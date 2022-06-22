# Sections

## Full width section
The full width component will create space using the tailwind class 'w-full'. 
```blade
<x-sections.full-width>
    Your content
</x-sections.full-width>
```

## structure
```blade
<div>
    <section class="">
        @isset($title)
            <h4>
                {{$title}}
            </h4>
        @endisset

        @isset($subtitle)
            <h6>{{$subtitle}}</h6>
        @endif
    </section>
    <div class="max-w-screen-xl mx-auto p-8">
        {{$slot}}
    </div>

</div>
```