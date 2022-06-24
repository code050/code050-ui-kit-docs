# Install now!

The simplest and fastest way to get up and running with the Code050 UI kit is by cloning the repo.

> Recommend creating a components folder inside resources

    root directory / resources / views / components

!> Currently not as a package available! Clone the repo into your project.

```git
git clone https://github.com/code050/code050-components.git .
```


## Tailwind

**Install Tailwind CSS**

Install tailwindcss and its peer dependencies via npm, and create your tailwind.config.js file.
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```

!> Tailwindcss modules @tailwindcss/typography and @tailwindcss/forms need to be installed seperately.

**Add Tailwind to your Laravel Mix configuration**

In your webpack.mix.js file, add tailwindcss as a PostCSS plugin.
```webpack.mix.js
mix.js("resources/js/app.js", "public/js")
  .postCss("resources/css/app.css", "public/css", [
    require("tailwindcss"),
  ]);
```

**Configure your template paths**

> Add the paths to all of your template files in your tailwind.config.js file. `tailwind.config.js`
<details>
    <summary>
        Tailwind config
    </summary>

```tailwind.config.js
const defaultTheme = require('tailwindcss/defaultTheme');
module.exports = {
    darkMode: 'class',
    content: [
        './vendor/laravel/framework/src/Illuminate/Pagination/resources/views/*.blade.php',
        './vendor/laravel/jetstream/**/*.blade.php',
        './storage/framework/views/*.php',
        './resources/views/**/*.blade.php',
        "./node_modules/flowbite/**/*.js"
    ],
    theme: {
        extend: {

            gradients: {
                'darkoverlay': "linear-gradient(0deg, rgba(2,0,36,1) 0%, rgba(0,0,0,1) 44%, rgba(0,0,0,0) 100%);",
            },
            colors: {
                transparent: 'transparent',
                'forest': {
                    'DEFAULT': '#00894A',
                    990: '#00210D',
                    950: '#00391B',
                    900: '#00522A',
                    800: '#006D3A',
                    700: '#00894A',
                    600: '#17A660',
                    500: '#40C178',
                    400: '#60DE92',
                    300: '#7EFBAC',
                    200: '#C1FFD3',
                    100: '#F3FFF3',
                },
                'jade': {
                    'DEFAULT': '677C6B',
                    990: '#0D1F13',
                    950: '#223427',
                    900: '#374B3C',
                    800: '#4F6353',
                    700: '#677C6B',
                    600: '#809684',
                    500: '#9BB09E',
                    400: '#B6CCB9',
                    300: '#D2E8D4',
                    200: '#E0F6E2',
                    100: '#F3FFF3',
                },
                'uranus': {
                    'DEFAULT': '#537D88',
                    990: '#001F26',
                    950: '#023640',
                    900: '#204C57',
                    800: '#3A646F',
                    700: '#537D88',
                    600: '#6D97A3',
                    500: '#88B2BE',
                    400: '#A2CDD9',
                    300: '#BEEAF7',
                    200: '#D5F6FF',
                    100: '#F6FDFF',
                },
                'lobster': {
                    'DEFAULT': '#DD3730',
                    990: '#410001',
                    950: '#680003',
                    900: '#930006',
                    800: '#BA1B1B',
                    700: '#DD3730',
                    600: '#FF5449',
                    500: '#FF897A',
                    400: '#FFB4A9',
                    300: '#FFDAD4',
                    200: '#FFEDE9',
                    100: '#FCFCFC',
                },
                'stone': {
                    'DEFAULT': '#757874',
                    990: '#121212',
                    950: '#292929',
                    900: '#383838',
                    800: '#5C5F5B',
                    700: '#757874',
                    600: '#8F918D',
                    500: '#A9ACA7',
                    400: '#C6C7C3',
                    300: '#E1E3DE',
                    200: '#F0F1EC',
                    100: '#FBFDF7',
                },
                'herb': {
                    'DEFAULT': '#717971',
                    990: '#161D17',
                    950: '#161D17',
                    900: '#414942',
                    800: '#586159',
                    700: '#717971',
                    600: '#8A938A',
                    500: '#A5ADA4',
                    400: '#C0C9BF',
                    300: '#DDE5DB',
                    200: '#EBF3E9',
                    100: '#F6FEF4',
                },
                'amber': {
                    'DEFAULT': '#FFC267',
                    990: '#AE6D09',
                    950: '#C88012',
                    900: '#D98D1A',
                    800: '#E89C29',
                    700: '#F9AC39',
                    600: '#FFB649',
                    500: '#FFC267',
                    400: '#FFCA7A',
                    300: '#FFD698',
                    200: '#FFDDAB',
                    100: '#FFECD0',
                }
            },
            fontFamily: {
                'headline': ['Raleway', ...defaultTheme.fontFamily.sans],
                'body': [
                    'nunito', defaultTheme.fontFamily.sans
                ],
                sans: [
                    'Nunito', ...defaultTheme.fontFamily.sans,
                ],
            },
            fontSize: {
                'display-lg': ['4rem', {
                    letterSpacing: '-.031rem',
                    lineHeight: '4.75rem'
                }],
                'display-md': ['3.563rem', {
                    letterSpacing: '-.016rem',
                    lineHeight: '4rem'
                }],
                'display-sm': ['2.813rem', {
                    letterSpacing: '0',
                    lineHeight: '3.25rem'
                }],
                'headline-lg': ['2rem', {
                    letterSpacing: '0',
                    lineHeight: '2.5rem'
                }],
                'headline-md': ['2rem', {
                    letterSpacing: '0',
                    lineHeight: '2.5rem'
                }],
                'headline-sm': ['2rem', {
                    letterSpacing: '0',
                    lineHeight: '2.5rem'
                }],
                'title-lg': ['1.375rem', {
                    letterSpacing: '0',
                    lineHeight: '2.5rem'
                }],
                'title-md': ['1rem', {
                    letterSpacing: '.006rem',
                    lineHeight: '1.5rem'
                }],
                'title-sm': ['.875rem', {
                    letterSpacing: '.006rem',
                    lineHeight: '1.25rem'
                }],
                'label-lg': ['.875rem', {
                    letterSpacing: '.006rem',
                    lineHeight: '1.25rem'
                }],
                'label-md': ['.75rem', {
                    letterSpacing: '.031rem',
                    lineHeight: '1rem'
                }],
                'label-sm': ['.688rem', {
                    letterSpacing: '.031rem',
                    lineHeight: '1rem'
                }],
                'body-lg': ['1rem', {
                    letterSpacing: '.031rem',
                    lineHeight: '1.5rem'
                }],
                'body-md': ['.875rem', {
                    letterSpacing: '.016rem',
                    lineHeight: '1.25rem'
                }],
                'body-sm': ['.75rem', {
                    letterSpacing: '.025rem',
                    lineHeight: '1rem'
                }],
            },
        },
    },
    daisyui: {
        themes: [
            {
                mytheme: {
                    "primary": "#0F8049",
                    "secondary": "#1EC875",
                    "accent": "#911BBA",
                    "neutral": "#454744",
                    "base-100": "#fff",
                    "base-200": "#efefef",
                    "base-300": "#E1E3DE",
                    "info": "#6D97A3",
                    "success": "#17A660",
                    "warning": "#FFAD40",
                    "error": "#FF5449",

                    "--rounded-box": "5px", // border radius rounded-box utility class, used in card and other large boxes
                    "--rounded-btn": "4px", // border radius rounded-btn utility class, used in buttons and similar element
                    "--rounded-badge": "1.9rem", // border radius rounded-badge utility class, used in badges and similar
                    "--animation-btn": "0.25s", // duration of animation when you click on button
                    "--animation-input": "0.2s", // duration of animation for inputs like checkbox, toggle, radio, etc
                    "--btn-text-case": "uppercase", // set default text transform for buttons
                    "--btn-focus-scale": "0.95", // scale transform of button when you focus on it
                    "--border-btn": "1px", // border width of buttons
                },
            }, 'luxury'
        ],
    },
    plugins: [
        require('@tailwindcss/forms'),
        require('@tailwindcss/typography'),
        require('daisyui'),
        require('flowbite/plugin')
    ],
};
```
</details>


## Fonts
The Code050 UI kit was designed with the Raleway and Nunito font in mind. So be sure to follow these instructions. For instance, via Google Web Fonts:

```style
<link href='https://fonts.googleapis.com/css?family=Raleway' rel='stylesheet'>
```

## Font icons
To use the font Icon component, you must first add the Font Awesome Icons font. Here are some instructions on how to do so:
```npm
npm install --save @fortawesome/fontawesome-free
```

> In order to to fully use the framework you need to install Daisy UI and Flowbite to make use of the required plugins.
```npm
npm i daisyui
```

```npm
npm i flowbite
```
```npm
npm i swiper
```
```npm
npm i animate.css
```
