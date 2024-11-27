## 问题解析

### transition 应该被放到啥位置？

`transition`属性在`CSS`中用于定义元素在某些属性变化时的过渡效果。它通常应该写在你希望应用过渡效果的元素的样式规则中。这里是一些关于transition属性的建议:

> https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition

- 直接在元素上: 如果元素本身需要过渡效果，你可以直接在元素的样式中添加transition属性

```css
button {
    transition: background-color 0.3s ease;
}
```

- 伪类或伪元素：当你希望在某个状态（如:hover, :focus等）时应用过渡效果，transition属性应放在基本状态的样式中

```css
button {
    background-color: #ccc;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #000;
}
```

- 使用类选择器：如果你想在特定条件下应用过渡效果，可以将transition添加到一个类选择器中

```css
.transition-effect {
    transition: all 0.5s ease;
}

button {
    background-color: #ccc;
}

button:hover {
    background-color: #000;
    transform: scale(1.1);
}
```

### 出于性能考虑

- 仅在需要时使用：不要为每个元素都设置过渡效果，只在需要过渡效果的元素上使用。
- 选择性地过渡属性：如果只需要某个或某些属性过渡，使用transition-property来指定，而不是使用all。
- 避免过多过渡：过多的过渡可能会影响性能，特别是在移动设备上。

## rgba

rgba(red, green, blue, alpha)

- red: 红
- green: 绿
- blue: 蓝
- alpha: 透明度