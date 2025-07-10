---
applyTo: '**'
---

# Key Rules for Setting Up i18n Routing with next-intl

## i18n Routing Options

- Use prefix-based (`/en/about`) routing.
- Use a `[locale]` dynamic segment in the App Router to serve localized content.

## Basic Setup

    - modify next.config.ts with next-intl
    ```
        import type { NextConfig } from 'next';
        import createNextIntlPlugin from 'next-intl/plugin';

        const nextConfig: NextConfig = {
          reactStrictMode: true,
        };

        const withNextIntl = createNextIntlPlugin();

        export default withNextIntl(nextConfig);
    ```
    - create middleware.ts
    ```
      import createMiddleware from 'next-intl/middleware';
      import {routing} from './i18n/routing';

      export default createMiddleware(routing);

      export const config = {
        // Match all pathnames except for
        // - … if they start with `/api`, `/trpc`, `/_next` or `/_vercel`
        // - … the ones containing a dot (e.g. `favicon.ico`)
        matcher: '/((?!api|trpc|_next|_vercel|.*\\..*).*)'
      };
    ```
    - create i18n/routing.ts
    ```
      import {defineRouting} from 'next-intl/routing';

      export const routing = defineRouting({
        locales: ['en', 'pt-br', 'es'],
        defaultLocale: 'en'
      });
    ```
    - create i18n/navigation.ts
    ```
      import { createNavigation } from 'next-intl/navigation';
      import { routing } from './routing';

      export const {Link, redirect, usePathname, useRouter} =
        createNavigation(routing);
    ```

    - create i18n/request.ts
    ```
      import {hasLocale} from 'next-intl';
      import {getRequestConfig} from 'next-intl/server';
      import {routing} from './routing';

      export default getRequestConfig(async ({requestLocale}) => {
        // Typically corresponds to the `[locale]` segment
        const requested = await requestLocale;
        const locale = hasLocale(routing.locales, requested)
          ? requested
          : routing.defaultLocale;

        return {
          locale,
          messages: (await import(`../../messages/${locale}.json`)).default
        };
      });
    ```

    - create app/[locale]/layout.tsx with NextIntlClientProvider
    ```
      import { NextIntlClientProvider } from 'next-intl/client'
    ```

    - create messages/en.json
    - create messages/pt-br.json
    - create messages/es.json

## Translations

- Store translations in JSON files (e.g., `messages/en.json`).
- Load translations dynamically based on the user’s locale.

## Configuration

- Use `next.config.mjs` to set up a `next-intl` plugin for request-specific i18n configurations.
- Define supported locales and a default locale in `routing.ts`.

## Middleware Integration

- Use middleware (`middleware.ts`) to handle locale negotiation and path matching (e.g., `/` → `/en`).

## Dynamic Locale Handling

- Implement a centralized configuration in `request.ts` to manage locale-specific settings and translations for Server Components.

## Component Integration

- Use `NextIntlClientProvider` in `layout.tsx` to pass translations and locale data to Client Components.
- Use hooks like `useTranslations` and `Link` in pages (e.g., `page.tsx`) for localized content and navigation.

## Static Rendering

- Add `generateStaticParams` to layouts or pages to enable static rendering for localized routes.
- Call `setRequestLocale` in each layout and page to validate the locale and enable static rendering before using `next-intl` APIs.

## Metadata Localization

- Use the `locale` param in metadata generation (`generateMetadata`) to provide localized titles or other metadata.

## Best Practices

- Always validate the incoming locale.
- Ensure that `setRequestLocale` is called before invoking any `next-intl` functionality.
- Customize routing and navigation APIs as needed while leveraging `next-intl` wrappers.

## Reference

<https://github.com/amannn/next-intl/tree/main/examples/example-app-router>
