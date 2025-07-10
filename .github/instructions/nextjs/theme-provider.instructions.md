---
applyTo: '**'
---
# Configure next-themes

    - create component ThemeProvider.tsx
    ```
      "use client";

      import { ThemeProvider as NextThemesProvider } from "next-themes";
      import { ComponentProps } from "react";

      type ThemeProviderProps = ComponentProps<typeof NextThemesProvider>;

      export function ThemeProvider({ children, ...props }: ThemeProviderProps) {
        return (
          <NextThemesProvider {...props}>
            {children}
          </NextThemesProvider>
        );
      }
    ```
    
    - wrap app/layout.tsx with ThemeProvider

    - create in Header component
        - toggle button to switch between light and dark themes
        - use shadcn/ui and lucide-react (Moon, Sun)

    - create components.json to configure shadcn/ui theme
    e.g.
    ```json
        {
        "style": "default",
        "rsc": true,
        "tailwind": {
            "config": "",
            "css": "app/globals.css",
            "baseColor": "neutral",
            "cssVariables": true
        },
        "aliases": {
            "components": "@/components",
            "utils": "@/lib/utils",
            "ui": "@/components/ui",
            "lib": "@/lib",
            "hooks": "@/hooks"
        },
        "iconLibrary": "lucide"
        }
    ```

    - create globals.css if not already created
