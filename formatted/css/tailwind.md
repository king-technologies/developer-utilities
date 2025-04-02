# Tailwind CSS


## Grid

### Grid Template Columns

```css
.mushroom-grid{
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
}
```

to 

```html

<div class="grid grid-cols-[repeat(auto-fill,minmax(200px,1fr))] gap-4">
    <!-- Grid Items -->
</div>
```