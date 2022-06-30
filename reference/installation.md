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
npm i @tailwindcss/forms
npm i @tailwindcss/typography
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

> Add a link to the stylesheet in the head
```html
<link href="{{ asset('css/app.css') }}" rel="stylesheet">
```
<details>
    <summary>
    contents of the app.css
    </summary>

```css
@import 'tailwindcss/base';
@import 'tailwindcss/components';
@import 'tailwindcss/utilities';
@import "animate.css";


h1 {
    @apply lg:text-display-lg text-display-md font-light font-headline;
}

h2 {
    @apply lg:text-display-md text-display-sm font-headline;
}

h3 {
    @apply lg:text-display-sm text-title-lg font-headline;
}

h4 {
    @apply text-title-lg font-headline;
}

h5 {
    @apply text-title-md font-headline;
}

h6 {
    @apply text-title-sm font-headline;
}

label {
    @apply font-semibold font-body;
}

p {
    @apply text-body-md font-body;
}

td {
    @apply py-2 text-primary hover:text-primary-focus;
}

.iconcard {
    @apply card hover:text-white focus:bg-primary focus:text-white hover:bg-primary focus:outline-0 py-6
}

.inactive.iconcard {
    @apply text-black bg-gray-300;
}

.active {
    @apply text-primary font-semibold;
}

/* The progress container (grey background) */
.progress-container {
    width: 100%;
    height: 4px;

    transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}

/* The progress bar (scroll indicator) */
.progress-bar {
    height: 4px;
    background: #17A660;
    width: 0%;

    transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}

@layer utilities {
    /* Chrome, Safari and Opera */
    .no-scrollbar::-webkit-scrollbar {
        display: none;
    }

    .no-scrollbar {
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }

    .swiper-slide {
        text-align: center;
        font-size: 18px;
        background: #fff;

        /* Center slide text vertically */
        display: -webkit-box;
        display: -ms-flexbox;
        display: -webkit-flex;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        -webkit-justify-content: center;
        justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
        -webkit-align-items: center;
        align-items: center;
    }

    /*.swiper-pagination-bullet {*/
    /*    width: 48px;*/
    /*    height: 48px;*/
    /*    bottom: 0px;*/
    /*}*/
    .swiper-slide img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    :root {
        --swiper-theme-color: #17A660;
    }
}

.navigation {
    @apply fixed mb-4 z-20 w-full text-gray-700 bg-white dark:text-stone-200 dark:bg-stone-950;
}

.navigation-mobile {
    @apply flex flex-col max-w-screen-xl px-4 mx-auto md:items-center md:justify-between md:flex-row md:px-6 lg:px-8;
}

.navigation-container {
    @apply flex flex-row items-center justify-between;
}

.navigation-logo {
    @apply py-4 w-20;
}

.navigation-toggle-open {
    @apply md:hidden rounded-lg focus:outline-none;
}

.navigation-item-container {
    @apply flex-col flex-grow pb-4 md:pb-0  md:flex md:justify-end md:flex-row;
}

.navigation-item {
    @apply px-4 py-2 mt-2 text-sm font-bold bg-transparent rounded-lg dark:bg-transparent dark:hover:bg-gray-600 dark:focus:bg-gray-600 dark:focus:text-white dark:hover:text-white dark:text-gray-200 md:mt-0 md:ml-4 hover:text-gray-900 focus:text-gray-900 hover:bg-gray-200 focus:bg-gray-200 focus:outline-none;
}

.navigation-theme-toggle {
    @apply text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-gray-400 dark:focus:ring-gray-700 rounded-lg text-sm p-2.5;
}

.navigation-theme-toggle-container {
    @apply flex;
}

.navigation-theme-toggle-modus {
    @apply ml-2 font-bold text-sm text-neutral dark:text-base-100;
}

.progress-bar-container {
    @apply progress-container bg-base-200 dark:bg-stone-900;
}

.category-span {
    @apply inline-block bg-primary rounded-full px-3 py-1 text-base font-semibold text-base-100 mr-2 mb-2;
}

.category-span-position {
    @apply absolute top-48 z-10 px-6;
}

.project-card {
    @apply dark:bg-stone-900 bg-base-200 relative rounded-t-xl overflow-hidden mb-8 mt-8;
}

.project-card-container {
    @apply rounded-t-xl;
}

.project-card-container-image-style {
    @apply w-full max-h-60 object-contain rounded-t-xl;
}

.project-card-content-container {
    @apply px-6 py-4 border-t dark:border-0 dark:bg-stone-990;
}

.project-card-container-image {
    @apply p-4 h-60 w-full object-cover flex rounded-t-xl items-center;
}

.project-card-content-title {
    @apply text-stone-990 dark:text-base-100 font-bold text-xl;
}

.project-card-content-subtext {
    @apply text-stone-990 dark:text-base-100 text-lg leading-relaxed;
}

.project-card-redirect {
    @apply py-4;
}

.blog {
    @apply flex mx-auto  max-w-screen-xl md:w-full lg:w-10/12 p-4 flex-col;
}

.blog-title-container {
    @apply pb-4;
}

.blog-title {
    @apply text-8xl;
}

.blog-date-container {
    @apply flex gap-1 pb-8;
}

.blog-content-container {
    @apply pb-4;
}

.blog-content-paragraph {
    @apply pb-4 pt-4 leading-8 text-lg;
}

.blog-image-container {
    @apply bg-error-content rounded w-full h-96;
}

.blog-image {
    @apply object-cover h-full w-full;
}

.consult-card {
    @apply md:w-1/2 pb-8 pr-8;
}

.consult-card-container {
    @apply border-2 h-48 border-primary dark:border-secondary rounded-2xl p-4
}

.consult-card-title {
    @apply mb-4 font-bold text-2xl text-primary dark:text-secondary;
}

.consult-card-content {
    @apply text-lg leading-6 text-stone-990 dark:text-base-200;
}

.swiper {
    @apply swiper-slide h-full dark:bg-stone-950;
}

.swiper-container {
    @apply h-full  flex flex-col md:flex-row border border-base-200 dark:border-stone-900 rounded-xl bg-white dark:bg-stone-990;
}

.swiper-container-image {
    @apply md:w-1/3 rounded-2xl;
}

.swiper-container-content {
    @apply flex h-full px-4 py-6;
}

.swiper-container-content-text {
    @apply text-left p-4;
}

.swiper-quote-icon {
    @apply text-primary text-6xl;
}

.swiper-blockquote {
    @apply relative p-4 text-xl italic border-l-4  text-neutral border-base-200;
}

.swiper-blockquote-slot {
    @apply text-lg mb-4 text-stone-990 dark:text-base-300;
}

.swiper-blockquote-title {
    @apply text-sm mb-4 text-stone-990 dark:text-base-300;
}

.swiper-blockquote-organisation {
    @apply text-primary dark:text-secondary;
}

.hero-button-container {
    @apply mt-5 sm:mt-8 md:w-1/2 sm:flex justify-center md:justify-start;
}

.hero {
    @apply flex-wrap flex  justify-around;
}

.hero-left-container {
    @apply sm:w-full md:w-1/2 pr-4  flex flex-col sm:pb-4 mt-8 md:mt-0 justify-center lg:h-full md:text-left;
}

.hero-left-container-heading {
    @apply tracking-tight font-bold text-neutral dark:text-base-100 text-4xl lg:text-6xl;
}

.hero-left-container-heading-span {
    @apply text-primary dark:text-secondary;
}

.hero-left-container-content {
    @apply mt-3 text-base text-gray-500 dark:text-gray-300 sm:mt-5 sm:max-w-xl md:mt-5 text-xl md:text-2xl lg:mx-0;
}

.hero-right-container {
    @apply sm:w-full flex md:pl-4 justify-center md:justify-start md:w-1/2 pt-12  my-auto;
}

.hero-right-container-image {
    @apply relative md:w-3/4;
}

.contact-form-feedback {
    @apply my-8 alert text-white bg-success dark:bg-secondary alert-success shadow-lg;
}

.contact-form {
    @apply my-4 flex flex-col gap-8 md:flex-row md:w-3/4;
}

.contact-form-container-left {
    @apply md:w-1/2;
}

.contact-form-container-right {
    @apply md:w-1/2;
}

.contact-form-textinput {
    @apply placeholder-white dark:placeholder-stone-950
    rounded-xl block px-4 w-full text-sm text-neutral
    bg-transparent border border-b-2 border-gray-300
    appearance-none dark:text-white dark:border-gray-400
    dark:focus:border-primary focus:outline-none focus:ring-0
    focus:border-primary h-11;
}

.contact-form-textarea {

    @apply placeholder-white dark:placeholder-stone-950
    rounded-xl block px-4 w-full h-full text-sm text-neutral
    bg-transparent border border-b-2 border-gray-300
    appearance-none dark:text-white dark:border-gray-400
    dark:focus:border-primary focus:outline-none focus:ring-0
    focus:border-primary h-52 top-1/2;

}

.contact-form-textinput-container {
    @apply relative z-0 mb-6;

}

.contact-form-label {
    @apply block mb-2 text-sm font-medium text-gray-900 dark:text-base-100;
}

.contact-form-text-input-label {
    @apply peer-focus:font-medium absolute text-sm text-neutral
    dark:text-base-100 duration-300 transform -translate-y-7
    scale-75 top-2.5 left-2.5 origin-[0]
    peer-focus:left-2.5 peer-focus:px-2.5
    peer-focus:text-primary peer-focus:dark:text-primary
    peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0
    peer-focus:scale-75 peer-focus:-translate-y-5 bg-white
    dark:bg-stone-950
}

.contact-form-textarea-input-label {
    @apply peer-focus:font-medium absolute text-sm text-neutral
    dark:text-base-100 duration-300 transform -translate-y-7
    scale-75 top-2.5 left-2.5 origin-[0]
    peer-focus:left-2.5 peer-focus:px-2.5
    peer-focus:text-primary peer-focus:dark:text-primary
    peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0
    peer-focus:scale-75 peer-focus:-translate-y-5 bg-white
    dark:bg-stone-950
}

.contact-form-select-label {
    @apply block mb-2 text-sm font-medium text-gray-900 dark:text-base-100;
}

.contact-form-select {
    @apply border-b-2 border border-gray-300 text-gray-900 text-sm rounded-xl focus:ring-primary focus:border-primary block w-full p-2.5 bg-white dark:bg-stone-950 dark:border-gray-400 dark:placeholder-gray-400 dark:text-base-100 dark:focus:ring-primary dark:focus:border-primary;
}

.contact-form-submit {
    @apply text-white bg-primary hover:bg-primary focus:ring-4 focus:outline-none focus:ring-primary font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-primary dark:hover:bg-primary dark:focus:ring-primary;
}

.contact-details-container {
    @apply md:w-3/4 mb-4 mt-8 gap-4 flex flex-wrap md:flex-nowrap md:flex-row pb-2;
}

.contact-detail-column {
    @apply w-full md:w-2/5 lg:w-1/3  pb-2 flex justify-start flex-col border border-primary dark:border-secondary rounded-xl;
}

.contact-detail-column-icon-row {
    @apply flex justify-center my-4 text-lg;
}

.contact-detail-column-icon {
    @apply fill-primary dark:fill-secondary w-4 text-2xl text-primary dark:text-secondary;
}

.contact-detail-column-content {
    @apply text-primary dark:text-secondary text-center font-bold leading-relaxed;
}

.text-component-container {
    @apply w-full md:w-1/2 px-3 mb-6 md:mb-0;
}

.text-component-label {
    @apply block uppercase tracking-wide text-primary dark:text-secondary text-xs font-bold mb-2;
}

.text-component-input {
    @apply appearance-none block w-full bg-base-100 text-base-content border border-error rounded py-3 px-4 mb-3 leading-tight focus:outline-none ;
}

.text-component-message {
    @apply text-error text-xs italic;
}

.team-member-mockup {
    @apply md:w-1/3 pr-8 mt-8 mb-8;
}

.team-member-image {
    @apply w-full pb-4;
}

.team-member-name {
    @apply text-xl font-bold pb-2 text-stone-990 dark:text-white;
}

.team-member-title {
    @apply text-lg text-stone-990 dark:text-white;
}

.project-redirect {
    @apply h-96 w-full p-4 rounded-xl;
}

.project-redirect-container {
    @apply h-96 flex flex-col md:w-1/3 space-y-4  justify-center;
}

.project-redirect-container-image {
    @apply w-32;
}

.project-redirect-container-title {
    @apply text-2xl text-primary dark:text-secondary font-bold;
}

.project-redirect-container-slot {
    @apply text-white text-lg leading-relaxed;
}

.activities-container {
    @apply flex flex-col md:flex-row flex-wrap justify-between pb-16;
}

.activities-container-left {
    @apply lg:w-1/2 mb-4;
}

.activities-container-left-heading {
    @apply text-4xl font-bold text-neutral dark:text-base-100;
}

.activities-container-left-redirect-container {
    @apply flex items-center pt-4;
}

.activities-container-left-redirect-slot {
    @apply text-lg lg:text-xl underline text-primary dark:text-secondary mb-4 mr-4;
}

.activities-container-left-redirect-slot-sub {
    @apply text-xl text-gray-600 dark:text-gray-200;
}

.activities-container-right {
    @apply lg:w-1/2 rounded-xl border bg-white dark:bg-stone-990 border-primary;
}

.activities-container-right-image-container {
    @apply flex flex-col md:flex-row;
}

.activities-container-right-image-container-container {
    @apply md:w-1/3 rounded-2xl;
}

.activities-container-right-image-container-container-image {
    @apply object-cover h-full w-full rounded-xl;
}

.activities-container-right-image-container-right {
    @apply md:w-2/3 flex py-4 flex-col;
}

.activities-container-right-image-container-right-container {
    @apply md:p-4 px-4 py-4 md:py-0;
}

.activities-container-right-image-container-right-sub {
    @apply text-stone-990 dark:text-base-300;
}

.activities-container-right-image-container-right-name {
    @apply text-xl mb-4 font-bold text-stone-990 dark:text-base-300;
}

.activities-container-right-image-container-right-content {
    @apply text-lg mb-4 text-stone-990 dark:text-base-300;
}

.full-width-section {
    @apply max-w-screen-xl mx-auto p-8;
}

.main-slider {
    @apply md:py-32;
}

.main-slider-additional {
    @apply flex justify-center text-center;
}

.main-slider-additional-text {
    @apply text-2xl text-primary dark:text-secondary;
}

.main-slider-container {
    @apply mt-8;
}

.main-slider-container-container {
    @apply md:h-72;
}

.why-us {
    @apply flex flex-row flex-wrap lg:flex-nowrap gap-8 py-8;
}

.why-us-left-column {
    @apply lg:w-1/3;
}

.why-us-left-column-content {
    @apply mb-4;
}

.why-us-left-column-heading {
    @apply font-bold text-2xl lg:text-4xl text-stone-990 dark:text-white mb-4;
}

.why-us-left-column-sub {
    @apply text-2xl text-stone-990 dark:text-white mb-2;
}

.why-us-left-column-redirects {
    @apply pt-4;
}

.why-us-left-column-href {
    @apply flex items-center pt-4;
}

.why-us-left-column-redirect-text {
    @apply text-lg lg:text-xl underline text-primary dark:text-secondary mb-4 mr-4;
}

.why-us-left-column-redirect-icon {
    @apply mr-2 text-primary dark:text-secondary sm:text-sm lg:text-xl;
}

.why-us-right-column {
    @apply lg:w-2/3;
}

.service-block {
    @apply max-w-sm flex mx-auto justify-start border-gray-300  border rounded py-2;
}

.service-block-image {
    @apply w-32;
}

.service-block-content {
    @apply w-3/4;
}

.development-block {
    @apply max-w-sm mx-auto flex justify-start flex-col border border-primary rounded p-2;
}

.explanatory-card {
    @apply flex flex-col justify-between items-start min-h-full text-neutral border dark:border-0 bg-base-200 dark:bg-stone-990
    dark:text-stone-200 md:w-1/2 lg:w-1/2 rounded-2xl p-4;
}

.explanatory-card-content {
    @apply space-y-4 p-4;
}

.explanatory-card-title {
    @apply text-2xl font-bold text-stone-990   dark:text-gray-200;
}

.explanatory-card-sub {
    @apply mb-8 text-lg leading-relaxed;
}

.explanatory-card-url {
    @apply p-4;
}

.explanatory-card-image {
    @apply bottom-0 relative space-y-4 m-4 h-60 rounded-xl bg-base-300 dark:bg-stone-950  pt-4 flex justify-center mb-4 p-4;
}

.plan-card {
    @apply max-w-sm rounded shadow-lg;
}

.usp {
    @apply md:w-1/3 py-4 pr-4;
}

.usp-icon-container {
    @apply flex flex-row my-auto items-center justify-start align-middle pr-2;
}

.usp-title {
    @apply pl-2 font-bold text-primary dark:text-secondary text-xl;
}

.usp-slot {
    @apply text-lg text-gray-900 dark:text-base-100;
}

.testimonial-block {
    @apply flex flex-row border border-gray-400 rounded p-4 max-w-xl;
}

.testimonial-block-image-container {
    @apply pr-4;
}

.testimonial-block-image {
    @apply relative right-0 object-cover min-h-full max-h-60;
}

.testimonial-block-quote-container {
    @apply sm:w-2/3 md:w-4/6 lg:w-3/4 flex flex-col;
}

.testimonial-block-quote-author {
    @apply flex;
}

.testimonial-block-qoute-org {
    @apply flex flex-wrap space-x-1;
}

.update {
    @apply mx-auto max-w-md p-4;
}

.update-container {
    @apply bg-indigo-400 rounded px-4 pt-4;
}

.update-header {
    @apply text-4xl text-white pb-4;
}

.update-sub {
    @apply text-white text-lg leading-relaxed pb-4;
}

.update-cta {
    @apply flex flex-col pb-8;
}

.update-cta-button {
    @apply pt-8 w-1/2;
}

.error-container {
    @apply container mt-5 pt-5;
}

.error-container-alert {
    @apply alert text-center;
}

.error-container-alert-content {
    @apply min-h-screen flex justify-center items-center;
}

.error-container-alert-content-container {
    @apply flex flex-col justify-center;
}

.error-container-alert-content-lottie {
    @apply dark:text-white text-xl my-8 text-center;
}

.error-container-alert-button {
    @apply bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded;
}

.default-page-head-section {
    @apply w-full pt-16;
}

.header-container {
    @apply pt-12 md:py-48;
}

.breadcrumb-container {
    @apply flex flex-col pb-4;
}

.breadcrumb-ordered-list {
    @apply inline-flex items-center space-x-1 md:space-x-3;
}

.breadcrumb-list-item {
    @apply inline-flex items-center;
}

.breadcrumb-list-item-first {
    @apply inline-flex items-center text-sm font-bold text-neutral hover:text-primary dark:text-base-100 dark:hover:text-white;
}

.breadcrumb-list-item-after {
    @apply flex items-center;
}

.breadcrumb-arrow-svg {
    @apply w-6 h-6 text-gray-400;
}

.breadcrumb-list-item-after-redirect {
    @apply ml-1 text-sm font-medium text-neutral hover:text-primary md:ml-2 dark:text-base-100 dark:hover:text-white;
}

.header-container {
    @apply md:justify-start;
}

.head-container-subcontainer {
    @apply sm:w-full md:w-1/2;
}

.header-container-subcontainer-container {
    @apply flex flex-col sm:pb-4 md:justify-center lg:h-full text-left;
}

.header-container-subcontainer-heading {
    @apply tracking-tight font-bold text-neutral dark:text-base-100 pb-4 text-4xl lg:text-6xl;
}

.header-container-subcontainer-subheading {
    @apply mt-3 text-base text-gray-500 dark:text-gray-300 sm:mt-5 sm:max-w-xl md:mt-5 text-xl md:text-xl lg:mx-0;
}

.project-short-section {
    @apply flex flex-col md:flex-row space-x-4;
}

.project-short-column-left {
    @apply md:w-1/2;
}

.project-short-column-left-title {
    @apply tracking-tight font-bold text-neutral dark:text-white pb-4 text-4xl
}

.project-short-column-left-subtitle {
    @apply dark:text-white leading-relaxed text-lg
}

.project-short-column-right {
    @apply pt-4 md:pt-0 md:w-1/2;
}

.project-long-section-title {
    @apply tracking-tight font-bold text-neutral dark:text-base-200 pb-4 text-4xl;
}

.project-long-section-container {
    @apply flex flex-col md:flex-row;
}

.project-long-section-content {
    @apply text-stone-990 dark:text-white leading-relaxed text-lg;
}

.full-width-screen {
    @apply w-full;
}

.full-width-screen-image {
    @apply w-full h-96 object-cover;
}

.redirect-header {
    @apply tracking-tight font-medium text-neutral dark:text-gray-100 pb-4 text-2xl;
}

.redirect-casus-container {
    @apply w-full flex flex-col flex-wrap md:flex-row justify-between;
}

.redirect-casus-column {
    @apply basis-1/3 md:pr-8;
}

.about-head-title {
    @apply dark:text-secondary text-neutral text-6xl font-bold pb-4;
}

.about-head-sub {
    @apply text-lg leading-relaxed dark:text-base-200;
}

.meet-the-team {
    @apply md:w-1/3;
}

.meet-the-team-heading {
    @apply font-bold text-4xl dark:text-secondary pb-4;
}

.meet-the-team-sub {
    @apply text-lg leading-relaxed text-stone-990 dark:text-base-200
}

.team-members-container {
    @apply flex flex-col md:flex-row flex-wrap flex-grow;
}

.fresh-container {
    @apply flex flex-row justify-between flex-wrap lg:flex-nowrap md:py-48;
}

.fresh-left {
    @apply lg:w-1/3 mb-4;
}

.fresh-left-heading {
    @apply text-4xl font-bold text-gray-800 dark:text-gray-200 mb-4;
}

.fresh-left-sub {
    @apply text-xl text-gray-800 dark:text-gray-200 mb-4;
}

.fresh-case-redirect {
    @apply flex items-center pt-4;
}

.fresh-case-redirect-text {
    @apply text-lg lg:text-xl underline text-stone-990 dark:text-white mb-4 mr-4;
}

.fresh-right {
    @apply lg:w-2/3 pl-4;
}

.fresh-right-background-image {
    @apply absolute top-0 left-0 rounded-xl;
}

.fresh-right-outline {
    @apply hidden md:block absolute top-0 left-0 mt-28 ml-36 border-0 md:border-2 border-secondary rounded-xl;
}

.fresh-right-foreground-image {
    @apply absolute top-0 left-0 mt-32 ml-40 rounded-xl;
}

.development-services-container {
    @apply flex flex-col md:flex-row flex-wrap
}

.development-services-container-description {
    @apply md:w-1/2 mb-4 pr-4 md:pl-4 md:pt-4;
}

.development-services-container-description-heading {
    @apply text-4xl font-bold text-neutral  dark:text-secondary mb-4
}

.development-services-container-description-sub {
    @apply text-lg leading-relaxed dark:text-white;
}

.best-container {
    @apply flex justify-center items-center;
}

.best-inner-container {
    @apply flex flex-col md:flex-row;
}

.best-inner-image-container {
    @apply md:w-1/2  mb-4 md:mb-0;
}

.best-inner-image {
    @apply pr-4 float-left w-full h-full object-cover;
}

.best-outer-container {
    @apply md:w-1/2;
}

.best-outer-heading {
    @apply pb-4 font-bold text-4xl text-primary dark:text-secondary;
}

.best-outer-sub {
    @apply text-neutral leading-relaxed text-xl dark:text-base-100;
}

.about-case-redirect-container {
    @apply bg-white dark:bg-stone-950 flex flex-col justify-center;
}

.about-activities-container {
    @apply flex flex-col justify-center;
}

.clients {
    @apply mb-4 py-8;
}

.clients-title {
    @apply flex justify-center text-lg text-stone-600 dark:text-base-100;
}

.client-collection {
    @apply flex gap-4 flex-wrap md:flex-nowrap justify-around;
}

.single-client {
    @apply object-contain w-20;
}

.casus-heading {
    @apply flex-wrap flex  justify-start;
}

.casus-heading-container {
    @apply sm:w-full md:w-1/2 pr-4;
}

.casus-heading-container-content {
    @apply flex flex-col sm:pb-4 mt-8 md:mt-0  text-left justify-center lg:h-full md:text-left;
}

.casus-heading-container-content-title {
    @apply tracking-tight font-bold text-neutral dark:text-gray-100 text-4xl lg:text-6xl;
}

.casus-heading-container-content-span {
    @apply text-primary dark:text-secondary;
}

.casus-heading-container-content-text {
    @apply mt-3 text-base text-gray-500 dark:text-gray-300 sm:mt-5 sm:max-w-xl md:mt-5 text-xl md:text-2xl lg:mx-0;
}

.casus-collection-container {
    @apply w-full flex flex-col flex-wrap md:flex-row justify-between;
}

.contact-head-container {
    @applu ;
}

.contact-head-text-container {
    @apply md:w-3/4;
}

.contact-head-text-heading {
    @apply md:w-3/4 text-4xl font-extrabold dark:text-base-100 pb-8;
}

.contact-head-text-sub {
    @apply md:w-3/4 text-lg dark:text-base-100 leading-relaxed pb-4;
}

.contact-form-wrapper {
    @apply mt-8 w-full;
}

.contact-form-wrapper-heading {
    @apply text-xl text-primary dark:text-secondary font-bold pb-4;
}

.custom-page-head-container {
    @apply bg-base-100 dark:bg-stone-950 overflow-hidden pb-4 w-1/2;
}

.custom-page-head-container-heading-wrapper {
    @apply font-bold text-4xl lg:text-6xl text-stone-950 dark:text-white;
}

.custom-page-head-container-heading {
    @apply font-bold text-4xl lg:text-6xl text-primary dark:text-secondary;
}

.custom-page-head-container-sub-wrapper {
    @apply pb-4
}

.custom-page-head-container-sub-text {
    @apply text-stone-950 dark:text-white leading-relaxed text-xl;
}

.custom-page-head-button {
    @apply md:w-1/2 sm:flex justify-center lg:justify-start mb-4 md:mb-0;
}

.custom-section-heading {
    @apply bg-base-100 dark:bg-stone-950 overflow-hidden pb-4 flex flex-wrap;
}

.custom-section-heading-header {
    @apply font-bold text-2xl lg:text-4xl text-stone-990 dark:text-white;
}

.custom-section-heading-header-second {
    @apply font-bold text-2xl lg:text-4xl text-primary dark:text-secondary;
}

.custom-page-items-container {
    @apply flex md:justify-start flex-wrap md:flex-nowrap lg:justify-between   gap-8 my-4;
}

.custom-info-section {
    @apply bg-base-100 dark:bg-stone-950 overflow-hidden pb-4 flex flex-wrap;
}

.custom-info-section-heading {
    @apply font-bold text-2xl lg:text-4xl text-stone-990 dark:text-white;
}

.custom-info-section-heading-second {
    @apply font-bold text-2xl lg:text-4xl text-primary dark:text-secondary;
}

.custom-info-section-text {
    @apply text-stone-950 leading-relaxed text-xl dark:text-base-100;
}

.custom-usp-header {
    @apply font-bold text-4xl my-2 dark:text-base-100;
}

.custom-usp-container {
    @apply flex flex-col pt-4 md:flex-row-reverse flex-wrap;
}

.custom-usp-column {
    @apply flex md:w-1/2 items-center flex-row gap-4 pb-4 align-super;
}

.custom-usp-mark-container {
    @apply bg-primary dark:bg-secondary w-8 h-8 flex justify-center items-center rounded-full;
}

.custom-usp-mark-svg {
    @apply fill-white my-4 w-4 text-2xl
}

.custom-usp-mark-svg-alternative {
    @apply fill-primary dark:fill-secondary my-4 w-4  text-2xl
}

.custom-usp-title {
    @apply text-gray-800 dark:text-base-200 text-base align-middle;
}

.section-advantage-header {
    @apply bg-base-100 dark:bg-stone-950  pb-4 flex flex-wrap;
}

.section-advantage-header-title {
    @apply font-bold text-2xl lg:text-4xl text-stone-990 dark:text-white
}

.section-advantage-header-second-title {
    @apply font-bold text-2xl lg:text-4xl text-primary dark:text-secondary
}

.advantage-usp-container {
    @apply flex flex-col md:flex-row flex-grow flex-wrap  -m-1;
}

.development-hero-wrapper {
    @apply flex-wrap flex-col md:flex-row flex justify-between;
}

.development-hero-wrapper-container {
    @apply pb-4 md:w-1/2 leading-relaxed;
}

.development-hero-title-black {
    @apply text-2xl md:text-4xl lg:text-6xl font-bold dark:text-base-100;
}

.development-hero-title-primary {
    @apply text-2xl md:text-4xl lg:text-6xl font-bold text-primary dark:text-secondary;
}

.development-hero-sub-container {
    @apply py-4;
}

.development-hero-sub-container-text {
    @apply text-xl dark:text-base-200 leading-relaxed;
}

.development-section-advantage {
    @apply flex flex-col justify-center items-center;
}

.development-section-advantage-wrapper {
    @apply flex flex-col  md:flex-row justify-between gap-8
}

.development-section-advantage-left-column {
    @apply flex md:w-1/2 flex-col space-y-4;
}

.development-section-advantage-left-column-title {
    @apply font-bold text-2xl dark:text-base-100;
}

.development-section-advantage-left-column-sub {
    @apply text-lg leading-relaxed dark:text-base-100;
}

.development-section-advantage-right-column {
    @apply md:w-1/2 rounded-xl;
}

.development-section-advantage-right-column-wrapper {
    @apply px-6 pb-4;
}

.development-section-advantage-right-column-wrapper-title {
    @apply font-bold text-2xl mb-2 dark:text-base-100;
}

.development-advantage-items-wrapper {
    @apply flex flex-col pt-4 md:flex-row-reverse flex-wrap;
}

.single-development-advantage-item {
    @apply flex md:w-1/2  flex-row gap-4 pb-4 align-super;
}

.single-development-advantage-item-wrapper {
    @apply bg-primary dark:bg-secondary min-w-[2rem] w-8 h-8 flex justify-center items-center rounded-2xl;
}

.single-development-advantage-item-svg {
    @apply fill-white my-4 w-4 text-2xl;
}

.single-development-advantage-item-text {
    @apply text-gray-800 dark:text-base-200 text-base align-middle;
}

.development-mood-image {
    @apply h-96 w-full p-4 rounded-xl pb-8;
}

.section-info-wrapper {
    @apply flex justify-center items-center;
}

.section-info-wrapper-container {
    @apply flex md:gap-4;
}

.section-info-wrapper-content {
    @apply md:w-1/2 md:pr-4;
}

.section-info-wrapper-content-text-container {
    @apply flex flex-col space-y-4 flex-wrap;
}

.section-info-wrapper-content-image {
    @apply block md:hidden w-1/2 flex justify-center items-center;
}

.section-info-title {
    @apply font-bold text-2xl mb-4 dark:text-base-100;
}

.section-info-title {
    @apply font-bold text-xl dark:text-base-200;
}

.section-info-sub {
    @apply text-lg leading-relaxed dark:text-base-200;
}

.section-info-image {
    @apply hidden md:block w-1/2 flex justify-center items-center;
}

.development-section-redirect {
    @apply flex flex-col justify-center;
}

.development-section-activities {
    @apply flex flex-col justify-center;
}

.section-explanatory-heading {
    @apply text-center mb-8;
}

.section-explanatory-title {
    @apply font-bold text-primary dark:text-secondary text-4xl;
}

.section-explanatory-sub-wrapper {
    @apply flex flex-col mt-4 pb-8;
}

.section-explanatory-sub-title {
    @apply font-bold text-gray-900 dark:text-gray-200 text-2xl;
}

.section-explanatory-sub-text {
    @apply pt-8 leading-relaxed text-xl text-gray-600 dark:text-gray-300;
}

.explanatory-cards-wrapper {
    @apply flex w-full flex-wrap md:flex-nowrap flex-col md:flex-row justify-around gap-8
}

.section-offer {
    @apply flex flex-col justify-center items-center pt-8 md:pt-0;
}

.section-offer-items-wrapper {
    @apply md:py-48 flex flex-col justify-center items-center;
}

.section-offer-items-wrapper-container {
    @apply flex flex-col justify-items-center;
}

.offer-header-container {
    @apply flex flex-col lg:w-full flex-wrap mt-4 pb-8;
}

.offer-title {
    @apply font-bold text-primary dark:text-secondary text-4xl lg:text-6xl
}

.offer-title-second {
    @apply font-bold  text-gray-900 dark:text-gray-200 text-2xl;
}

.offer-sub-text {
    @apply pt-8 leading-relaxed text-xl text-gray-600 dark:text-gray-200;
}

.offer-services-container {
    @apply flex flex-col md:flex-row md:justify-start lg:justify-between flex-wrap my-4;
}

.offer-svg {
    @apply fill-primary dark:fill-secondary my-4 w-4 text-2xl mr-2 text-primary dark:text-secondary;
}

.home-testimonial-section {
    @apply flex  flex-col justify-center;
}

.custom-header-container {
    @apply flex flex-col md:flex-row;
}

.left-custom {
    @apply w-full md:w-1/2
}

.custom-head-image {
    @apply flex justify-center w-full md:w-1/2;
}

```

<details>

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
