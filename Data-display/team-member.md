# Team members

Team members blocks to display each member and their job title

---


![](./../_media/examples/teammember/teammember.png)

---

> parameters
<br>
**$image** - string
<br>
**$title** - string
<br>
**$name** - string
---

```blade
<x-mockup.teammember>
    <x-slot:image> route to image </x-slot:image>
    <x-slot:name> name </x-slot:name>
    <x-slot:title> title </x-slot:title>
</x-mockup.teammember>
```

```.html
<div class="md:w-1/3 pr-8 mt-8 mb-8">
    <img class="w-full pb-4" src="{{$image}}" alt="team member"/>
    <div>
        <h1 class="text-xl font-bold pb-2 text-stone-990 dark:text-white">{{$name}}</h1>
        <p class="text-lg text-stone-990 dark:text-white">{{$title}}</p>
    </div>
</div>
```