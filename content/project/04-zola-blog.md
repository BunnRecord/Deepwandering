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

## 回到顶部按钮

html 代码：
```
<!-- 添加回到顶部按钮 -->
<button id="back-to-top" title="回到顶部">↑</button>

<script>
// 添加回到顶部功能
document.addEventListener('DOMContentLoaded', function() {
  const backToTopButton = document.getElementById("back-to-top");

  // 当用户滚动超过 300px 时显示按钮
  window.addEventListener('scroll', function() {
    if (window.pageYOffset > 300) {
      backToTopButton.style.display = "block";
    } else {
      backToTopButton.style.display = "none";
    }
  });

  // 点击按钮时回到顶部
  backToTopButton.addEventListener("click", function() {
    window.scrollTo({
      top: 0,
      behavior: "smooth"
    });
  });
});
</script>
```

css 样式：

```
#back-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: none;
  background-color: var(--primary-color, #333);
  color: white;
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 24px;
  cursor: pointer;
  opacity: 0.7;
  transition: opacity 0.3s;
  z-index: 1000;
}

#back-to-top:hover {
  opacity: 1;
}
```