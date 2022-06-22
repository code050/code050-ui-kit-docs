# Cards

## Case
![image](./../../_media/examples/cards/project-card.png)

### Usage
> parameters
<br>
**$title** - string
<br>
**$categorie** - string
<br>
**$slot** - string
---

```blade
<x-cases.card>
    <x-slot:title>Title</x-slot:title>
    <x-slot:style>Additional option for styling the imag<x-slot:style>
    Text here will be placed in the subtext p tag.
    <x-slot:image>https://helpx.adobe.com/content/dam/heen/photoshop/using/convert-color-image-black-whijcr_content/main-pars/before_and_after/image-befoLandscape-Color.jpg</x-slot:image>
    <x-slot:url>#</x-slot:url>
</x-cases.card>
```

### Structure
```blade
<div class="project-card">
    <div class="project-card-container">
        <div class="category-span-position">
            <span class="category-span">
                {{$categorie}}
            </span>
        </div>
        <!-- -->
        @if ($style->isNotEmpty())
            <div class="project-card-container-image {{$style}}">
                @else
                    <div class="project-card-container-image">
                        @endif
                        <img class="project-card-container-image-style" src="{{$image}}" alt="">
                    </div>
                    <div class="project-card-content-container">
                        <p class="project-card-content-title">{{$title}}</p>
                        <p class="project-card-content-subtext">{{ substr($slot ?? '', 0,50)}}...</p>
                        <div class="project-card-redirect">
                            <a href="#">
                                <x-ui.buttons.small.alternative-outline>
                                    Website bezoeken
                                </x-ui.buttons.small.alternative-outline>
                            </a>
                        </div>
                    </div>
            </div>
    </div>
</div>
```

## Consult
![image](./../../_media/examples/cards/consult.png)
> parameters
<br>
**$title** - string
<br>
**$slot** - string
---
### Usage
```blade
<x-cards.consult>
  <x-slot:title>CARD TITLE</x-slot:title>
  SLOT TEXT GOES HERE
</x-cards.consult>
```

### Structure
```.blade
<div class="consult-card">
    <div class="consult-card-container">
        <h1 class="consult-card-title">{{$title}}</h1>
        <p class="consult-card-content">{{$slot}} </p>
    </div>
</div>
```


## Explanatory
![image](./../../_media/examples/cards/explanatory.png)
> parameters
<br>
**$title** - string
<br>
**$slot** - string
---
### Usage
```blade
<x-service.explanatory-card>
  <x-slot:title>TITLE GOES HERE</x-slot:title>
  SLOT TEXT GOES HERE
  <x-slot:image><img class="rounded-xl px-4" width="600" height="400" src="#" alt=""/></x-slot:image>
  <x-slot:url>ROUTE TO DESITINATION</x-slot:url>
</x-service.explanatory-card>
```

### Structure
```.blade
<div class="explanatory-card">
    <div class="explanatory-card-content">
        <h3 class="explanatory-card-title">{{$title}}</h3>
        <p class="explanatory-card-sub">{{$slot}}</p>
    </div>
    <div class="inline-block bottom-0">
        <div class="explanatory-card-url">
            <a href="{{$url}}">
                <x-ui.buttons.small.primary>
                    Meer lezen
                </x-ui.buttons.small.primary>
            </a>
        </div>
        <div class="explanatory-card-image">
            {{$image}}
        </div>
    </div>
</div>

```
