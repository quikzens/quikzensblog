---
title: "Button dengan animasi loading"
date: 2021-05-23T18:41:59+08:00
---

{{< rawhtml >}}
<div class="demo">
  <h2>Demo</h2>
  <style>
    /* base styles */
    .button {
      position: relative;
      overflow: hidden;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.8rem 2rem;
      font-family: inherit;
      font-size: 16px;
      background: transparent;
      border: 0;
      border-radius: 0.5rem;
      color: #f7f7f7;
      cursor: pointer;
      outline: none;
      transition-property: background, box-shadow;
      transition-duration: 0.35s;
    }

    .button span {
      position: relative;
      display: flex;
      align-items: center;
      z-index: 1;
    }

    /* loading state */
    @keyframes loadingKeyframes {
      0% {
        transform: translateX(25px);
      }
      100% {
        transform: translateX(-20px);
      }
    }

    .button.loading::before,
    .button.loading span {
      cursor: wait;
    }

    .button.loading::before {
      content: "";
      position: absolute;
      z-index: 1;
      top: 0;
      left: -100%;
      width: 300%;
      height: 100%;
      background: #5d2fdf repeating-linear-gradient(60deg, transparent, transparent 10px, #5526c5 10px, #5526c5 20px);
      animation: loadingKeyframes 1s infinite linear;
    }

    .button.loading span {
      opacity: 0.5;
    }
  </style>
  <button class="button loading">
    <span>Lagi loading bro!</span>
  </button>
</div>
{{</ rawhtml >}}

## HTML

```html
<button class="button loading">
  <span>Tunggu sebentar bro!</span>
</button>
```

## CSS

```css
/* base styles */
.button {
  position: relative;
  overflow: hidden;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.8rem 2rem;
  font-family: inherit;
  font-size: 16px;
  background: transparent;
  border: 0;
  border-radius: 0.5rem;
  color: #f7f7f7;
  cursor: pointer;
  outline: none;
  transition-property: background, box-shadow;
  transition-duration: 0.35s;
}

.button span {
  position: relative;
  display: flex;
  align-items: center;
  z-index: 1;
}

/* loading state */
@keyframes loadingKeyframes {
  0% {
    transform: translateX(25px);
  }
  100% {
    transform: translateX(-20px);
  }
}

.button.loading::before,
.button.loading span {
  cursor: wait;
}

.button.loading::before {
  content: "";
  position: absolute;
  z-index: 1;
  top: 0;
  left: -100%;
  width: 300%;
  height: 100%;
  background: #5d2fdf repeating-linear-gradient(60deg, transparent, transparent 10px, #5526c5 10px, #5526c5 20px);
  animation: loadingKeyframes 1s infinite linear;
}

.button.loading span {
  opacity: 0.5;
}
```