# Footer
![](./../../_media/examples/footer/footer.png)
```blade
<footer class="bg-white dark:bg-stone-950">
    <div class="hidden md:block bg-white dark:bg-stone-950">
        <x-sections.full-width>
            <div class="w-full relative h-1 xl:mt-10">
                <div class=" absolute z-10 -top-8 xl:-top-24 -right-6 w-1/2 border-12 bg-primary bg-opacity-5 p-5 rounded-full aspect-square">
                    <div class="border-12 bg-primary bg-opacity-5 p-5 rounded-full aspect-square">
                        <img src="{{asset('assets/images/photos/mood/kantine.webp')}}" loading="lazy" alt="collega's" class="rounded-full w-full aspect-square object-cover"/>
                    </div>
                </div>
            </div>
        </x-sections.full-width>
    </div>

    <!--Circle using clippath-->
    <div style="clip-path: ellipse(130% 100% at 50% 100%);" class=" bg-primary pt-8 text-white z-9">
        <x-sections.full-width>
            <div class="container ">
                <div class="flex">
                    <div class="flex flex-col">
                        <div class="py-6 flex flex-col justify-start space-y-4">
                            <p class="text-4xl font-bold">{{__('Maatwerk applicatie?')}}</p>
                            <p class="text-2xl pb-8">{{__('Het begint bij uw idee!')}}</p>
                            <a href="#">
                                <x-ui.buttons.large.white>
                                    call to action
                                </x-ui.buttons.large.white>
                            </a>
                        </div>
                        <div class="pt-8 flex flex-col space-y-4">
                            <p class="text-md">+12 345678</p>
                            <p class="text-md">info@mail.nl</p>
                            <p class="text-md">Adres 1337</p>
                            <p class="text-md">zipcode, city</p>
                        </div>
                    </div>
                </div>
            </div>
        </x-sections.full-width>
        <div class="flex justify-center text-center items-center h-16" style="background-color: rgba(0, 0, 0, 0.2);">
            © {{ now()->year }}&nbsp;
            <a class="text-whitehite" href="#">title</a>
        </div>
    </div>
</footer>
```