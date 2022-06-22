# Hero
![](./../../_media/examples/hero/hero.png)

```blade
@section('Hero')
    <meta name="description" content="This is the landingpage of code050">
@overwrite
<div class="hero">
	<!--Left section-->
    <div class="hero-left-container">
    	<!--Breadcrumb-->
        <nav class="breadcrumb-container" aria-label="Breadcrumb">
            <ol class="breadcrumb-ordered-list">
                <li class="breadcrumb-list-item">
                    <a class="breadcrumb-list-item-first" href="#">
                        <svg class="mr-2 w-4 h-4" fill="currentColor" viewBox="0 0 20 20"
                             xmlns="http://www.w3.org/2000/svg"><path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"></path></svg>
                        <b>Home</b>
                    </a>
                </li>
            </ol>
        </nav>
        <h1 class="hero-left-container-heading">Wij maken<span class="hero-left-container-heading-span">webapplicaties op maat</span></h1>
        <p class="hero-left-container-content">Subtitle</p>
        <div class="hero-button-container">
            <a href="#">
                <x-ui.buttons.large.primary>Meer informatie</x-ui.buttons.large.primary>
            </a>
        </div>
    </div>

    <!--Image-->
    <div class="hero-right-container">
        <img class="hero-right-container-image" width="600" height="400" loading="lazy" src="{{asset('assets/images/svg/undraw/undraw_building_blocks.svg')}}" alt="">
    </div>
</div>
```