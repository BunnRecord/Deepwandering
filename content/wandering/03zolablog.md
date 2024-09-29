+++
title = "博客相关"
date = 2024-09-29
updated = 2024-09-29

+++

## 图片显示
目前图片显示有两种的方式：直接 markdown 插入和通过 html 和 css 的组合插入。

直接 markdown 插入：

```markdown
![小狗疑心大宇宙阴谋篡夺它的位置](/resource/image.png)
```

通过 html 和 css 的组合插入：

html 代码：

```html
<figure class="image-container">
  <img src="/resource/image.png" alt="小狗疑心大宇宙阴谋篡夺它的位置" />
  <figcaption class="image-caption">小狗疑心大宇宙阴谋篡夺它的位置</figcaption>
</figure>
```

css 样式：

```css
.image-container {
  text-align: center;
  margin-left: 0;
}

.image-container img {
  width: 40%;
  height: auto;
}

.image-caption {
  font-style: italic;
  color: #666;
  margin-top: 5px;
}
```     
