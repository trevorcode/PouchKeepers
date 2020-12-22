# How to actually install Tailwind into a static site

Use 
    npm i postcss-cli tailwindcss autoprefixer cssnano

Then make a package.json
    {
        "scripts": {
            "buildcss": "postcss dist/tailwind.css -o dist/tailwind.min.css"
        },
        "dependencies": {
            "autoprefixer": "^10.1.0",
            "cssnano": "^4.1.10",
            "postcss": "^8.2.1",
            "postcss-cli": "^8.3.1",
            "tailwindcss": "^2.0.2"
        }
    }

Then postcss.config.js

    // postcss.config.js
    module.exports = {
    plugins: {
            tailwindcss: {},
            autoprefixer: {},
            cssnano:
            {preset: 'default'},
        }
    }

use

    npm run buildcss

Should minfy and build your tailwind stuff if you have your tailwind configured correctly.

Tailwind.config.js

    module.exports = {
    purge: {
        enabled: true,
        content: [
            './**/*.html',
            './**/*.razor'
        ],
    },
    darkMode: false, // or 'media' or 'class'
    theme: {
        extend: {
        colors: {
            primary: {
            100: 'var(--color-primary-100)',
            200: 'var(--color-primary-200)',
            300: 'var(--color-primary-300)',
            400: 'var(--color-primary-400)',
            500: 'var(--color-primary-500)',
            600: 'var(--color-primary-600)',
            700: 'var(--color-primary-700)',
            800: 'var(--color-primary-800)',
            900: 'var(--color-primary-900)'
            }
        },
        },
        
    },
    variants: {
        extend: {},
    },
    plugins: [],
    }
