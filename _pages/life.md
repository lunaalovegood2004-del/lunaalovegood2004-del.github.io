---
layout: archive
title: "我的生活"
permalink: /life/
author_profile: true
author: "Name Name"
---

研究生生活并不只有课程、论文和实习。



## 日常记录

研究生开学，进入新的人生旅程。

## 兴趣与爱好

暑假在家练习厨艺！

<div class="life-photo-deck" aria-label="我的做饭照片集">
  <div class="life-photo-stack" id="cooking-photo-stack">
    <div class="life-photo-card"><img src="{{ '/images/IMG_4766做饭.jpeg' | relative_url }}" alt="我的做饭记录 1"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_4816做饭.jpeg' | relative_url }}" alt="我的做饭记录 2"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_4853做饭.jpeg' | relative_url }}" alt="我的做饭记录 3"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_4859做饭.jpeg' | relative_url }}" alt="我的做饭记录 4"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_4860做饭.jpeg' | relative_url }}" alt="我的做饭记录 5"></div>
  </div>
  <p class="life-photo-hint">悬停在照片上，慢慢翻一翻。</p>
</div>

## 冰淇淋大赏

我很喜欢吃冰淇淋，所以决定把这里留给我的冰淇淋收藏。每一张照片，都是我吃过、喜欢过的一种味道。

这一组照片先做成一个小小的“冰淇淋大赏”。把鼠标放到照片上，最上面的一张会滑到后面，下一张自然露出来，像翻一沓真实的照片。

<div class="life-photo-deck" aria-label="我的冰淇淋照片集">
  <div class="life-photo-stack" id="life-photo-stack">
    <div class="life-photo-card"><img src="{{ '/images/IMG_0055.jpeg' | relative_url }}" alt="我最爱的冰淇淋 1"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0118.jpeg' | relative_url }}" alt="我最爱的冰淇淋 2"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0208.jpeg' | relative_url }}" alt="我最爱的冰淇淋 3"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0362.jpeg' | relative_url }}" alt="我最爱的冰淇淋 4"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0452.jpeg' | relative_url }}" alt="我最爱的冰淇淋 5"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0672.jpeg' | relative_url }}" alt="我最爱的冰淇淋 6"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0836.jpeg' | relative_url }}" alt="我最爱的冰淇淋 7"></div>
    <div class="life-photo-card"><img src="{{ '/images/IMG_0974.jpeg' | relative_url }}" alt="我最爱的冰淇淋 8"></div>
  </div>
  <p class="life-photo-hint">悬停在照片上，慢慢翻一翻。</p>
</div>

<style>
.life-photo-deck { margin: 2.5rem 0 3rem; text-align: center; }
.life-photo-stack { position: relative; width: min(100%, 470px); height: 560px; margin: 0 auto; }
.life-photo-card { position: absolute; left: 50%; top: 50%; width: 360px; padding: 10px 10px 34px; background: #fff; border: 1px solid rgba(0,0,0,.12); box-shadow: 0 10px 28px rgba(0,0,0,.13); transform-origin: 50% 90%; transform: translate(-50%, -50%) rotate(0deg); transition: transform .45s ease, box-shadow .45s ease, opacity .45s ease; cursor: pointer; }
.life-photo-card img { display: block; width: 100%; height: auto; max-width: none; object-fit: contain; image-rendering: auto; }
.life-photo-card:nth-child(1) { transform: translate(-50%, -50%) rotate(-3deg); z-index: 8; }
.life-photo-card:nth-child(2) { transform: translate(-50%, -50%) rotate(2deg); z-index: 7; }
.life-photo-card:nth-child(3) { transform: translate(-50%, -50%) rotate(-2deg); z-index: 6; }
.life-photo-card:nth-child(4) { transform: translate(-50%, -50%) rotate(4deg); z-index: 5; }
.life-photo-card:nth-child(5) { transform: translate(-50%, -50%) rotate(-4deg); z-index: 4; }
.life-photo-card:nth-child(6) { transform: translate(-50%, -50%) rotate(2deg); z-index: 3; }
.life-photo-card:nth-child(7) { transform: translate(-50%, -50%) rotate(-1deg); z-index: 2; }
.life-photo-card:nth-child(8) { transform: translate(-50%, -50%) rotate(3deg); z-index: 1; }
.life-photo-stack:hover .life-photo-card { box-shadow: 0 16px 34px rgba(0,0,0,.17); }
.life-photo-card.is-moving { transform: translate(28%, -60%) rotate(9deg) !important; opacity: .98; z-index: 20 !important; }
.life-photo-hint { margin: .75rem 0 0; font-size: .85rem; opacity: .65; }
@media (max-width: 600px) { .life-photo-stack { height: 470px; } .life-photo-card { width: min(82vw, 300px); } }
@media (prefers-reduced-motion: reduce) { .life-photo-card { transition: none; } }
</style>

<script>
(function () {
  var stacks = document.querySelectorAll('.life-photo-stack');
  stacks.forEach(function (stack) {
    var timer = null;
    var moving = false;
    function flipPhoto() {
      if (moving || !stack.matches(':hover')) return;
      var first = stack.firstElementChild;
      if (!first) return;
      moving = true;
      first.classList.add('is-moving');
      setTimeout(function () {
        first.classList.remove('is-moving');
        stack.appendChild(first);
        moving = false;
      }, 450);
    }
    stack.addEventListener('mouseenter', function () { if (timer) return; timer = setInterval(flipPhoto, 900); });
    stack.addEventListener('mouseleave', function () { clearInterval(timer); timer = null; });
  });
})();
</script>

## 最近的生活

这个页面会随着研究生生活继续更新。课程、阅读、实习、旅行，以及一些普通但值得记住的日子，都可以成为这里的内容。

<!-- sidebar author profile -->
