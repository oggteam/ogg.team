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
            <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
            <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -9" result="goo" />
            <feComposite in="SourceGraphic" in2="goo" operator="atop"/>
          </filter>
        </defs>
      </svg>
    </div>
    <div class="slide slide_2">
      <h1>Yes, just f&#9880;cking three dots!</h1>
    </div>
    <div class="slide slide_3">
      <h1>Because that's simple &#38; effective</h1>
    </div>
    <div class="slide slide_4">
      <h1>Who we are?</h1>
    </div>
    <div class="slide slide_5">
      <h1>
        We are
        <ul class="word-wrap">
          <li class="word">design</li>
          <li class="word">web</li>
          <li class="word">identity</li>
          <li class="word">graphics</li>
          <li class="word">front-end</li>
        </ul>
        </h1>
    </div>
    <div class="slide slide_6">
      <h1>Are you ready?</h1>
      <p>
        <a class="btn btn_violet" href="mailto:ogg.design.team@gmail.com">Start a project</a>
      </p>
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
    }
  }
}
</script>


<style lang="less">
.wrapper {
  height: 100%;
  width: 100%;
}

// *****
// Nav
// *****
.nav {
  bottom: 20px;
  display: flex;
  font-size: 2rem;
  justify-content: space-around;
  left: 0;
  list-style: none;
  margin: 3rem 0;
  padding: 0;
  position: absolute;
  right: 0;
}
.nav_item_link {
  margin: 0 3rem;
  text-decoration: none;
  &:hover {
    text-decoration: underline;
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
  a {
    color: #fff;
  }
}
// Slide 1
.slide_1 {
  transform: translateX(0);
}

// Slide 2
.slide_2 {
  animation-delay: 5s;
  animation-name: anim_slide_2;
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
  animation-delay: 7s;
  animation-duration: 5s;
  animation-name: anim_slide_3;
}
@keyframes anim_slide_3 {
  0% {
    transform: translateX(100);
  }
  40%,60% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

// Slide 4
.slide_4 {
  animation-delay: 10s;
  animation-name: anim_slide_4;
}
@keyframes anim_slide_4 {
  0% {
    transform: translateX(100);
  }
  40%, 60% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

// Slide 5
.slide_5 {
  animation-delay: 12.4s;
  animation-duration: 8s;
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
  animation-delay: 18.6s;
  animation-duration: 7s;
  animation-fill-mode: forwards;
  animation-name: anim_slide_6;
  opacity: 0;
  transform: translateX(0);
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
  animation-delay: 0.1s;
  animation-duration: 7s;
  animation-fill-mode: forwards;
  animation-name: dots-move-top;
  filter: url("#goo");
  left: calc(50% - 115px);
  position: absolute;
  top: calc(50% - 18px);
  @media (min-width: 768px) {
    animation-delay: 0.1s, 17.5s;
    animation-duration: 7s, 2s;
    animation-name: dots-move-top, dots-move-left;
  }
}
@keyframes dots-move-top {
  0%, 65% {
    top:calc(50% - 18px);
  }
  100% {
    top:35px;
  }
}
@keyframes dots-move-left {
  0%,65% {
    left: calc(50% - 115px);
  }
  100% {
    left:20px;
  }
}
.dots__item {
  background-color: #fff;
  border-radius: 50%;
  height: 36px;
  left: 0;
  position: absolute;
  top: 0;
  width: 36px;
}
.dots__item_first {
  animation-delay: 0.3s;
  animation-direction: alternate;
  animation-duration: 1s;
  animation-iteration-count: 7;
  animation-name: moveLeftRight;
}
.dots__item_center {
  transform: translateX(100px);
}
.dots__item_last {
  animation-delay: 0.3s;
  animation-direction: alternate;
  animation-duration: 1s;
  animation-iteration-count: 7;
  animation-name: moveRightLeft;
  transform: translateX(200px);
}
@keyframes moveLeftRight {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(200px);
  }
}
@keyframes moveRightLeft {
  0% {
    transform: translateX(200px);
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
}
@media (min-width: 768px) {
  .word-wrap {
    display: inline-block;
    margin: 0 0 0 15px;
    min-width: 300px;
  }
}
.word {
  animation-duration: 7.5s;
  animation-iteration-count: infinite;
  animation-name: anim;
  opacity: 0;
  position: absolute;
  text-decoration: underline;
}
@media (max-width: 767px) {
  .word {
    left: 20px;
    right: 20px;
  }
}
.word:nth-child(2) {
  animation-delay: 1.5s;
}
.word:nth-child(3) {
  animation-delay: 3s;
}
.word:nth-child(4) {
  animation-delay: 4.5s;
}
.word:nth-child(5) {
  animation-delay: 6s;
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

</style>
