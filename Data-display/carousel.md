# Carousel
A website carousel or slider, is an effective way of displaying multiple images or content in a single space. It not only helps in saving screen space, but also encourages visitors to focus on important website content and improves the overall visual appeal effectively.
![image](./../../_media/examples/swiper/swiper.gif)
---
## install Swiper
!> Make sure Swiper.Js is intalled and add the folowing snippet in your page

```npm
npm install swiper
```

```cdn
<link rel="stylesheet" href="https://unpkg.com/swiper@8/swiper-bundle.min.css"/>

<script src="https://unpkg.com/swiper@8/swiper-bundle.min.js"></script>
```

```.js
<script src="{{ asset('./assets/swiper.js') }}"></script>
<!-- Initialize Swiper -->
<script>
    var swiper = new Swiper(".mySwiper", {
        spaceBetween: 30,
        centeredSlides: true,
        watchSlidesProgress: true,
        autoplay: {
            delay: 7000,
            disableOnInteraction: false,
        },
        pagination: {
            el: ".swiper-pagination",
            clickable: true,
        },
        navigation: {
            nextEl: ".swiper-button-next",
            prevEl: ".swiper-button-prev",
        },
    });
</script>
```

## Swiper component
> parameters
<br>
**$image** - string
<br>
**$title** - string
<br>
**$categorie** - string
<br>
**$slot** - string

### Usage

```.html
<!-- Slider main container -->
<div class="mt-8">
    <div class="swiper mySwiper md:h-72">
        <div class="swiper-wrapper">
            <x-cards.swiper-slide>
                <x-slot:image> route to image </x-slot:image>
                <x-slot:title>lorem ipsum</x-slot:title>
                lorem ipsum
                <x-slot:categorie>lorem ipsum</x-slot:categorie>
            </x-cards.swiper-slide>
        </div>
        <div class="py-4">
            <!--Additional buttons for navigation-->
            <div class="hidden swiper-button-next"></div>
            <div class="hidden swiper-button-prev"></div>
            <div class="swiper-pagination"></div>
        </div>
    </div>
</div>
```
### Swiper slide structure
```blade
<div class="swiper-slide swiper">
    <div
        class="swiper-container">
        <div class="swiper-container-image">
            @if ($image->isNotEmpty())
                <img class="object-cover md:h-32 rounded-xl"width="300" height="600" src="{{$image}}" alt=""/>
            @else
                <img class="object-cover md:h-32 rounded-xl" loading="lazy" width="300" height="600" src="SOURCE IMAGE" alt="No image found"/>
            @endif
        </div>
        <div class="swiper-container-content">
            <div class="swiper-container-content-text">
                <i class="swiper-quote-icon fa-solid fa-quote-left"></i>
                <blockquote class="swiper-blockquote">
                    <p class="swiper-blockquote-slot">{{$slot}}</p>
                    <p class="swiper-blockquote-title">{{$naam}}, {{$functie}}</p>
                    <p class="swiper-blockquote-organisation">{{$organisatie}}</p>
                </blockquote>
            </div>
        </div>
    </div>
</div>
```
### Styling
> Additional styling regarding the code050 guidelines

```style
<style>
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
    .swiper-slide img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    :root {
        --swiper-theme-color: ;
    }
</style>
```
