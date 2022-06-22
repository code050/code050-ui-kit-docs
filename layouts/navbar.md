# Navbar
!> import script for mobile users

Without the script in required section the menu will not be usable for user accessing the menu on mobile.
<details>
<summary>
Required javascript!
</summary>

```js
<script>
    // On page load or when changing themes, best to add inline in `head` to avoid FOUC
    if (localStorage.getItem('color-theme') === 'dark' || (!('color-theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        document.documentElement.classList.add('dark');
    } else {
        document.documentElement.classList.remove('dark')
    }

    var themeToggleDarkIcon = document.getElementById('theme-toggle-dark-icon');
    var themeToggleLightIcon = document.getElementById('theme-toggle-light-icon');

    // Change the icons inside the button based on previous settings
    if (localStorage.getItem('color-theme') === 'dark' || (!('color-theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        themeToggleLightIcon.classList.remove('hidden');
    } else {
        themeToggleDarkIcon.classList.remove('hidden');
    }

    var themeToggleBtn = document.getElementById('theme-toggle');

    themeToggleBtn.addEventListener('click', function () {

        // toggle icons inside button
        themeToggleDarkIcon.classList.toggle('hidden');
        themeToggleLightIcon.classList.toggle('hidden');

        // if set via local storage previously
        if (localStorage.getItem('color-theme')) {
            if (localStorage.getItem('color-theme') === 'light') {
                document.documentElement.classList.add('dark');
                localStorage.setItem('color-theme', 'dark');
            } else {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('color-theme', 'light');
            }

            // if NOT set via local storage previously
        } else {
            if (document.documentElement.classList.contains('dark')) {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('color-theme', 'light');
            } else {
                document.documentElement.classList.add('dark');
                localStorage.setItem('color-theme', 'dark');
            }
        }

    });
</script>
```
</details>

---

```blade
<!--basic navbar-->
<div class="navigation">
    <div x-data="{ open: false }"
         class="navigation-mobile">
        <div class="navigation-container">
            <div>
                <a href="#">
                    <img class="navigation-logo" height="" width="" src="LOGO SOURCE"alt="code050-logo" aria-label="">
                </a>
            </div>
            <button class="navigation-toggle-open focus:shadow-outline" aria-label="search" @click="open = !open">
                <svg fill="currentColor" viewBox="0 0 20 20" class="w-6 h-6">
                    <path x-show="!open" fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM9 15a1 1 0 011-1h6a1 1 0 110 2h-6a1 1 0 01-1-1z" clip-rule="evenodd"></path>
                    <path x-show="open" fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd"></path>
                </svg>
            </button>
        </div>
        <nav class="navigation-item-container hidden" :class="{'flex': open, 'hidden': !open}">
            <a class="navigation-item focus:shadow-outline" href="#">page</a>
            <a class="navigation-item focus:shadow-outline" href="#">page</a>
            <a class="navigation-item focus:shadow-outline" href="#">page</a>
            <a class="navigation-item focus:shadow-outline" href="#">page</a>

            <!---------------------------->
            <!--Language dialog goes her-->
            <!---------------------------->

            <button id="theme-toggle" type="button" class="navigation-theme-toggle">
                <div class="navigation-theme-toggle-container">
                    <svg id="theme-toggle-dark-icon" class="hidden w-5 h-5" fill="#ebc815" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                        <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path>
                    </svg>
                    <svg id="theme-toggle-light-icon" class="hidden w-5 h-5" fill="#ffbf00" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                        <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path>
                    </svg>
                    <p class="navigation-theme-toggle-modus">mode</p>
                </div>
            </button>
        </nav>
    </div>

    <!--progress bar-->
    <div class="progress-bar-container">
        <div class="progress-bar" id="myBar"></div>
    </div>
</div>
```

> optional language dialog

```blade
<!--Language dialog-->
<div @click.away="open = false" class="relative mr-4" x-data="{ open: false }">
    <button @click="open = !open" class="flex flex-row items-center w-full px-4 py-2 mt-2 text-sm font-bold text-left rounded-lg dark:bg-transparent dark:focus:text-white dark:hover:text-white dark:focus:bg-gray-600 dark:hover:bg-gray-600 md:w-auto  md:mt-0 md:ml-4 hover:text-gray-900 focus:text-gray-900 hover:bg-gray-200 focus:bg-gray-200 focus:outline-none focus:shadow-outline">
        <span class="uppercase flex items-center gap-2">
            <img src="IMAGE SOURCE" alt="" class="w-4 h-2"/>NL</span>
                <svg fill="currentColor" viewBox="0 0 20 20" :class="{'rotate-180': open, 'rotate-0': !open}" class="inline w-4 h-4 mt-1 ml-1 transition-transform duration-200 transform md:-mt-1">
                    <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd"></path>
                </svg>
    </button>
    <div class="z-10  absolute right-0 w-full mt-2 origin-top-right rounded-md shadow-lg " x-show="open" x-transition:enter="transition ease-out duration-100" x-transition:enter-start="transform opacity-0 scale-95" x-transition:enter-end="transform opacity-100 scale-100" x-transition:leave="transition ease-in duration-75" x-transition:leave-start="transform opacity-100 scale-100" x-transition:leave-end="transform opacity-0 scale-95">
	    <div class="px-2 py-2 bg-white rounded-md shadow dark:bg-stone-990">
			<a class=" block px-4 py-2 mt-2 text-sm font-bold bg-transparent rounded-lg dark:bg-transparent dark:hover:bg-stone-600 dark:focus:bg-stone-600 dark:focus:text-white dark:hover:text-white dark:text-stone-200 md:mt-0 hover:text-gray-900 focus:text-gray-900 hover:bg-gray-200 focus:bg-gray-200 focus:outline-none focus:shadow-outline flex gap-2 items-center justify-center" href="#">
	            <img src="{{asset('./assets/images/svg/flags/nl.svg')}}" alt="" class="w-4 h-2"/>NL</a>
	        <a class="block px-4 py-2 mt-2 text-sm font-bold bg-transparent rounded-lg dark-mode:bg-transparent dark-mode:hover:bg-gray-600 dark-mode:focus:bg-gray-600 dark-mode:focus:text-white dark-mode:hover:text-white dark-mode:text-gray-200 md:mt-0 hover:text-gray-900 focus:text-gray-900 hover:bg-gray-200 focus:bg-gray-200 focus:outline-none focus:shadow-outline flex gap-2 items-center justify-center" href="#">
	            <img src="{{asset('./assets/images/svg/flags/en.svg')}}" alt="" class="w-4 h-2"/> EN</a>
	    </div>
	</div>
</div>
```

!> <b>Note</b> the dialog needs to be placed inside nav element