# CSS Grid

```css
.parent{
    width: 100%
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    justify-content: center;
    
    .child{
        width: 300px;
        height: 400px;
    }
}
```