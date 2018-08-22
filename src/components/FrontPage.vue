<template>
  <div class="wrapper">
    <div class="slide slide_1">
      <div class="dots">
        <div class="dots__item dots__item_first"></div>
        <div class="dots__item dots__item_center"></div>
        <div class="dots__item dots__item_last"></div>
      </div>
      <svg xmlns="http://www.w3.org/2000/svg" version="1.1">
        <defs>
          <filter id="goo">
            <feGaussianBlur in="SourceGraphic" stdDeviation="6" result="blur" />
            <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 15 -6" result="goo" />
            <feComposite in="SourceGraphic" in2="goo" operator="atop"/>
          </filter>
        </defs>
      </svg>
    </div>
    <div v-bind:class="{ hide: isHide}">
      <button class="btn btn_skip" type="button" v-on:click="hideSlide">Skip</button>
      <div class="slide slide_2">
        <h1>Just 3 dots...</h1>
      </div>
      <div class="slide slide_3">
        <h1>...instead of many words</h1>
      </div>
      <div class="slide slide_4">
        <h1>Who we are?</h1>
      </div>
      <div class="slide slide_5">
        <h1>
          We are
          <ul class="word-wrap">
            <li class="word">your new brand</li>
            <li class="word">your new site</li>
            <li class="word" style="margin-top: -35px;">a live <img src="/static/images/heart.gif" height="150" /></li>
            <li class="word">...</li>
            <li class="word">badass creators</li>
          </ul>
        </h1>
      </div>
    </div>
    <div class="slide slide_6" v-bind:class="{ hide: isHide}">
      <h1>Are you ready?</h1>
      <a class="btn btn_violet" href="mailto:ogg.design.team@gmail.com">Work together</a>
      <div class="collapse navbar-collapse">
        <ul class="nav">
          <li class="nav_item">
            <router-link class="nav_item_link" to="/about">About</router-link>
          </li>
          <li class="nav_item">
            <router-link class="nav_item_link" to="/portfolio">Portfolio</router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FrontPage',
  data () {
    return {
      isHide: false
    }
  },
  methods: {
    hideSlide () {
      this.isHide = true
    }
  },
  created () {
    if(sessionStorage.getItem('hide_intro')) {
      this.isHide = true
    } else {
      sessionStorage.setItem('hide_intro', true)
    }
  }
}
</script>


<style lang="less">
.wrapper {
  height: 100%;
  width: 100%;
}
.hide {
  display: none;
}

// *****
// Nav
// *****
.nav {
  bottom: 20px;
  display: flex;
  font-size: 0.75rem;
  justify-content: space-around;
  left: 0;
  list-style: none;
  margin: 3rem 0;
  padding: 0;
  position: absolute;
  right: 0;
}
.nav_item_link {
  transition: color 0.3s;
  position: relative;
  text-transform: uppercase;
  text-decoration: none;
  letter-spacing: 5px;
  color: #fff6;
  &:hover,
  &:focus {
    color: #fff;
    text-decoration: none;
    &:before {
      color: #fff;
      text-shadow: 10px 0 #fff, -10px 0 #fff;
    }
  }
  &:before {
    position: absolute;
    top: 100%;
    left: 50%;
    color: transparent;
    content: '•';
    text-shadow: 0 0 transparent;
    transition: text-shadow 0.3s, color 0.3s;
    transform: translateX(-50%);
    pointer-events: none;
  }
}

// *****
// Slide
// *****
.slide {
  align-content: center;
  align-items: center;
  animation-duration: 4s;
  bottom: 0;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  height: 100%;
  justify-content: center;
  left: 0;
  padding: 0 20px;
  position: fixed;
  right: 0;
  text-align: center;
  top: 0;
  transform: translateX(100%);
  width: 100%;
}
// Slide 1
.slide_1 {
  transform: translateX(0);
}

// Slide 2
.slide_2 {
  animation-delay: 2.2s;
  animation-name: anim_slide_2;
  animation-duration: 3.6s;
  opacity: 0;
  transform: translateX(0);
}
@keyframes anim_slide_2 {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
    transform: translateX(0);
  }
  100% {
    opacity: 1;
    transform: translateX(-100%);
  }
}

// Slide 3
.slide_3 {
  animation-delay: 4s;
  animation-duration: 5s;
  animation-name: anim_slide_3;
}
@keyframes anim_slide_3 {
  0% {
    transform: translateX(100);
  }
  30%, 70% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

// Slide 4
.slide_4 {
  animation-delay: 7.6s;
  animation-name: anim_slide_4;
}
@keyframes anim_slide_4 {
  0% {
    transform: translateX(100);
  }
  30%, 70% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

// Slide 5
.slide_5 {
  animation-delay: 10.2s;
  animation-duration: 10s;
  animation-name: anim_slide_5;
  @media (max-width: 767px) {
    margin-top: -50px;
  }
}
@keyframes anim_slide_5 {
  0% {
    transform: translateX(100);
  }
  20%,80% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

// Slide 6
.slide_6 {
  animation-fill-mode: forwards;
  animation-duration: 5s;
  animation-delay: 2.2s;
  animation-name: anim_slide_6;
  opacity: 0;
  transform: translateX(0);
  &:not(.hide) {
    animation-delay: 18.3s;
    animation-duration: 7s;
  }
}
@keyframes anim_slide_6 {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

// *****
// Dots
// *****
.dots {
  filter: url("#goo");
  left: calc(50% - 32px);
  position: absolute;
  // top: 35px;
// }
// .dots:not(.noMove) {
  animation-delay: 0.1s;
  animation-duration: 3s;
  animation-fill-mode: forwards;
  animation-name: dots-move-top;
  top: calc(50% - 7px);
}
@keyframes dots-move-top {
  0%, 65% {
    top: calc(50% - 7px);
  }
  100% {
    top: 35px;
  }
}
.dots__item {
  background-color: #fff;
  // border-radius: 50%;
  height: 15px;
  left: 0;
  position: absolute;
  top: 0;
  width: 15px;
}
.dots__item_first {
  animation-delay: 0.3s;
  animation-direction: alternate;
  animation-duration: 0.55s;
  animation-iteration-count: 3;
  animation-name: moveLeftRight;
}
.dots__item_center {
  transform: translateX(25px);
}
.dots__item_last {
  animation-delay: 0.3s;
  animation-direction: alternate;
  animation-duration: 0.55s;
  animation-iteration-count: 3;
  animation-name: moveRightLeft;
  transform: translateX(50px);
}
@keyframes moveLeftRight {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(50px);
  }
}
@keyframes moveRightLeft {
  0% {
    transform: translateX(50px);
  }
  100% {
    transform: translateX(0);
  }
}






@media (min-width: 768px) {
  h1 {
    display: flex;
  }
}


.word-wrap {
  list-style: none;
  margin: 0;
  padding: 0;
  text-align: left;
}
@media (min-width: 768px) {
  .word-wrap {
    display: inline-block;
    margin: 0 0 0 15px;
    padding: 0 25px 0 0;
    width: 320px;
  }
}
.word {
  align-items: center;
  // animation-delay: 14.4s;
  animation-delay: 11.3s;
  animation-duration: 7.5s;
  animation-fill-mode: forwards;
  animation-iteration-count: 1;
  animation-name: anim;
  display: flex;
  justify-content: center;
  opacity: 0;
  position: absolute;
}
@media (max-width: 767px) {
  .word {
    left: 20px;
    right: 20px;
  }
}
.word:nth-child(2) {
  // animation-delay: 1.5s;
  animation-delay: 12.8s;
}
.word:nth-child(3) {
  animation-delay: 14.3s;
}
.word:nth-child(4) {
  animation-delay: 15.8s;
}
.word:nth-child(5) {
  animation-delay: 17.3s;
  animation-name: anim-last;
}
@keyframes anim {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  6.66% {
    opacity: 1;
    transform: translateY(0);
    transition: transform 0.38s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }
  20% {
    opacity: 1;
    transform: translateY(0);
    transition: transform 0.38s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }
  26.66% {
    opacity: 0;
    transform: translateY(-100%);
    transition: transform 0.32s cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
  100% {
    opacity: 0;
    transform: translateY(-100%);
    transition: transform 0.32s cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
}
@keyframes anim-last {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  6.66% {
    opacity: 1;
    transform: translateY(0);
    transition: transform 0.38s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }
  20% {
    opacity: 1;
    transform: translateY(0);
    transition: transform 0.38s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }
  26.66% {
    opacity: 1;
    transform: translateY(0);
    // transition: transform 0.32s cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
    // transition: transform 0.32s cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
}
</style>
