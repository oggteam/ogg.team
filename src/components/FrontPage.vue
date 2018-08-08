<template>
  <div class="wrapper">
    <section class="slider slider-1">
      <div class="dots">
        <div class="dots__item"></div>
        <div class="dots__item"></div>
        <div class="dots__item"></div>
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
    </section>
    <section class="slider slider-2">
      <h1>Yes, just f&#9880;cking 3 dots!</h1>
    </section>
    <section class="slider slider-3">
      <h1>Because that's simple &#38; effective</h1>
    </section>
    <section class="slider slider-4">
      <h1>Who we are?</h1>
    </section>
    <section class="slider slider-5">
      <h1>We are design</h1>
    </section>
  </div>
</template>

<script>
export default {
  name: 'FrontPage',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>


<style scoped>
  .wrapper {
    height: 100%;
    width: 100%;
  }
  .slider {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-content: center;
    align-items: center;
    text-align: center;
    height: 100%;
    width: 100%;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    transform: translateX(100%);
    animation-duration: 4s;
  }
  .slider-1 {
    transform: translateX(0);
    /* animation-name: fadeIn1;
    animation-duration: 3s;
    animation-delay: 2s;
    animation-fill-mode: forwards; */
  }
  .slider-2 {
    opacity: 0;
    transform: translateX(0);
    animation-delay: 5s;
    animation-name: fadeIn-sl2;
  }
  @keyframes fadeIn-sl2 {
    0% {opacity: 0;}
    50% {
      opacity: 1;
      transform: translateX(0);
    }
    100% {
      opacity: 1;
      transform: translateX(-100%);
    }
  }

  .slider-3 {
    animation-delay: 7s;
    animation-name: wobble121;
    animation-duration: 5s;
  }
  @keyframes wobble121 {
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





  .slider-4 {
    animation-delay: 10s;
    animation-name: wobble-sl4;
  }
  @keyframes wobble-sl4 {
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



  .slider-5 {
    animation-delay: 12.4s;
    animation-duration: 7s;
    animation-name: wobble-1;
  }
  @keyframes wobble-1 {
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




  @keyframes fadeIn1 {
    0%, 50% {opacity: 0;}
    100% {opacity: 1;}
  }
  @keyframes fadeIn {
    0% {opacity: 0;}
    50% {opacity: 1;}
    100% {opacity: 0;}
  }








.dots {
  filter: url("#goo");
  position: absolute;
  top: calc(50% - 18px);
  left: calc(50% - 115px);
  animation-duration: 7s, 2s;
  animation-delay: 0.1s, 16.7s;
  animation-name: dots-move-top, dots-move-left;
  animation-fill-mode: forwards;
}
@keyframes dots-move-top {
  0%,65% {top:calc(50% - 18px);}
  100% {top:35px;}
}
@keyframes dots-move-left {
  0%,65% {left: calc(50% - 115px);}
  100% {left:35px;}
}
.dots__item {
  width: 36px;
  height: 36px;
  position: absolute;
  top: 0;
  left: 0;
  background-color: #fff;
  border-radius: 50%;
}
.dots__item:nth-child(1) {
  animation: upDown 1.0s 0.3s infinite alternate;
  animation-iteration-count: 7;
}
.dots__item:nth-child(2) {
  transform: translateX(100px);
}
.dots__item:nth-child(3) {
  transform: translateX(200px);
  animation: rightLeft 1.0s 0.3s infinite alternate;
  animation-iteration-count: 7;
}
@keyframes upDown {
  0% {transform: translateX(0);}
  100% {transform: translateX(200px);}
}
@keyframes rightLeft {
  0% {transform: translateX(200px);}
  100% {transform: translateX(0);}
}
</style>
