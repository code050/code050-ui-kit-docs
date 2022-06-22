# Dropdown dialog
Dialogs inform users about a task and can contain critical information, require decisions, or involve multiple tasks.

> A Dialog is a type of modal window that appears in front of app content to provide critical information or ask for a decision. Dialogs disable all app functionality when they appear, and remain on screen until confirmed, dismissed, or a required action has been taken.

!> Dialogs are purposefully interruptive, so they should be used sparingly.


```.html
<div x-show="open"
    x-transition:enter="transition ease-out duration-100"
    x-transition:enter-start="transform opacity-0 scale-95"
    x-transition:enter-end="transform opacity-100 scale-100"
    x-transition:leave="transition ease-in duration-75"
    x-transition:leave-start="transform opacity-100 scale-100"
    x-transition:leave-end="transform opacity-0 scale-95"
    class="z-10  absolute right-0 w-full mt-2 origin-top-right
    rounded-md shadow-lg ">
    <div class="px-2 py-2 bg-white rounded-md shadow dark:bg-stone-990">
    <a class=" block px-4 py-2 mt-2 text-sm font-bold bg-transparent
        rounded-lg dark:bg-transparent dark:hover:bg-stone-600
        dark:focus:bg-stonedark:focus:text-white dark:hover:text-white
        dark:text-stone-200 md:mt-0 hover:text-gray-900 focus:text-gray-900
        hover:bg-gray-200 focus:bg-grayfocus:outline-none
        focus:shadow-outline flex gap-2 items-center justify-center
    " href="#">
        LANGUAGE #1
    </a>
    <a class="block px-4 py-2 mt-2 text-sm font-bold bg-transparent
    rounded-lg dark-mode:bg-transparent dark-mode:hover:bg-gray-600
    dark-mode:focus:bg-graydark-mode:focus:text-white dark-mode:hover:text-white
    dark-mode:text-gray-200 md:mt-0 hover:text-gray-900 focus:text-gray-900
    hover:bg-grayfocus:bg-gray-200 focus:outline-none focus:shadow-outline
    flex gap-2 items-center justify-center "
    href="#">
        LANGUAGE #2
    </a>
</div>
```