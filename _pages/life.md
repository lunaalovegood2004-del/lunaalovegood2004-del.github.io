---
layout: archive
title: "我的生活"
permalink: /life/
author_profile: true
author: "Name Name"
---

研究生生活并不只有课程、论文和实习。

我也想把这个网站留一小块空间，记录那些和专业没有直接关系、但构成了我的日常的事情。

## 日常记录

这里会慢慢放一些生活中的小片段，不追求完整，也不追求固定的更新频率。

## 兴趣与爱好

我希望把自己真正喜欢的事情记录下来，而不是为了让个人网站看起来“丰富”而堆砌内容。

## 照片

这一组照片先做成一个小小的“照片叠”，而不是把照片一张张竖着排下来。把鼠标放到照片上，最上面的一张会滑到后面，下一张自然露出来，像翻一沓真实的照片。

<div class="life-photo-deck" aria-label="生活照片集">
  <div class="life-photo-stack" id="life-photo-stack">
    <div class="life-photo-card"><img src="{{ '/images/IMG_0055.HEIC' | relative_url }}" alt="生活照片 1"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0118.HEIC' | relative_url }}" alt="生活照片 2"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0208.HEIC' | relative_url }}" alt="生活照片 3"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0362.HEIC' | relative_url }}" alt="生活照片 4"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0452.HEIC' | relative_url }}" alt="生活照片 5"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0672.HEIC' | relative_url }}" alt="生活照片 6"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0836.HEIC' | relative_url }}" alt="生活照片 7"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0974.HEIC' | relative_url }}" alt="生活照片 8"></div>
  </div>
  <p class="life-photo-hint">悬停在照片上，慢慢翻一翻。</p>
</div>

<style>
.life-photo-deck { margin: 2.5rem 0 3rem; text-align: center; }
.life-photo-stack { position: relative; width: min(100%, 430px); height: 520px; margin: 0 auto; perspective: 1000px; }
.life-photo-card { position: absolute; left: 50%; top: 50%; width: min(78%, 330px); aspect-ratio: 3 / 4; padding: 10px 10px 34px; background: #fff; border: 1px solid rgba(0,0,0,.12); box-shadow: 0 10px 28px rgba(0,0,0,.13); transform-origin: 50% 90%; transform: translate(-50%, -50%) rotate(var(--rotation, 0deg)); transition: transform .45s ease, box-shadow .45s ease, opacity .45s ease; cursor: pointer; overflow: hidden; }
.life-photo-card img { display: block; width: 100%; height: 100%; object-fit: cover; opacity: 0; transition: opacity .25s ease; }
.life-photo-card img.is-ready { opacity: 1; }
.life-photo-stack:hover .life-photo-card { box-shadow: 0 16px 34px rgba(0,0,0,.17); }
.life-photo-card.is-moving { transform: translate(28%, -60%) rotate(9deg) !important; opacity: .98; z-index: 20 !important; }
.life-photo-hint { margin: .75rem 0 0; font-size: .85rem; opacity: .65; }
@media (max-width: 600px) { .life-photo-stack { height: 440px; } .life-photo-card { width: min(82%, 300px); } }
@media (prefers-reduced-motion: reduce) { .life-photo-card { transition: none; } }
</style>

<script src="https://cdn.jsdelivr.net/npm/heic2any@0.0.4/dist/heic2any.min.js"></script>
<script>
(function () {
  var stack = document.getElementById('life-photo-stack');
  if (!stack) return;

  var images = stack.querySelectorAll('img');
  images.forEach(function (img) {
    fetch(img.src)
      .then(function (response) { return response.blob(); })
      .then(function (blob) {
        return heic2any({ blob: blob, toType: 'image/jpeg', quality: 0.88 });
      })
      .then(function (result) {
        var converted = Array.isArray(result) ? result[0] : result;
        img.src = URL.createObjectURL(converted);
        img.classList.add('is-ready');
      })
      .catch(function () {
        img.style.opacity = '1';
      });
  });

  var timer = null;
  var moving = false;
  function flipPhoto() {
    if (moving || !stack.matches(':hover')) return;
    var first = stack.firstElementChild;
    if (!first) return;
    moving = true;
    first.classList.add('is-moving');
    setTimeout(function () { first.classList.remove('is-moving'); stack.appendChild(first); moving = false; }, 450);
  }
  stack.addEventListener('mouseenter', function () { if (timer) return; timer = setInterval(flipPhoto, 900); });
  stack.addEventListener('mouseleave', function () { clearInterval(timer); timer = null; });
})();
</script>

## 最近的生活

这个页面会随着研究生生活继续更新。课程、阅读、实习、旅行，以及一些普通但值得记住的日子，都可以成为这里的内容。
