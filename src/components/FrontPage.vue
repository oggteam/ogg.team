<template>
  <div class="wrapper">
    <section class="slider slider-1">
      <div class="dots">
        <div class="dots-wrapper">
          <div class="dots-items">
            <div class="dots-item">
              <div class="dots-item-button dots-item-button--orange">
              </div>
            </div>
            <div class="dots-item">
              <div class="dots-item-button dots-item-button--pink">
              </div>
            </div>
            <div class="dots-item">
              <div class="dots-item-button dots-item-button--blue">
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="slider slider-2">
      <h1>Yes, just f*cking 3 dots!</h1>
    </section>
    <section class="slider slider-3">
      <h1>Bacause that's simple & effective</h1>
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
  #app,
  .wrapper {
    height: 100%;
    width: 100%;
  }
  .slider {
    /* animation:  1s infinite ease-in-out; */
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
    animation-duration: 3s;
  }
  .slider-1 {
    transform: translateX(0);
    animation-name: fadeIn1;
    animation-duration: 3s;
    animation-delay: 2s;
    animation-fill-mode: forwards;
  }
  .slider-2 {
    opacity: 0;
    transform: translateX(0);
    animation-delay: 5s;
    animation-name: fadeIn;
  }
  .slider-3 {
    animation-delay: 8s;
    animation-name: wobble;
  }
  .slider-4 {
    animation-delay: 11s;
    animation-name: wobble;
  }
  .slider-5 {
    /* transform: translateX(0); */
    animation-delay: 13s;
    animation-duration: 7s;
    /* animation-name: wobble-1, wobble-2, wobble-3; */
    animation-name: wobble-1;
  }
  @keyframes wobble-first {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
  @keyframes wobble {
    0% {
      transform: translateX(100);
    }
    50% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
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



.dots-wrapper {
	transform: translate(-50%, -50%);
  position: absolute;
  top: 50%;
      animation-duration: 7s;
    animation-name: wobble-trt;
    animation-fill-mode: forwards;
}
 @keyframes wobble-trt {
    0%,75% {top: 50%;}
    100% {top:35px;}
  }



.dots-item-button {
	border-radius: 50%;
}


.dots-items {
  transition-timing-function: cubic-bezier(0.64, 0.57, 0.67, 1.53);
}

.dots-item:nth-child(1) .dots-item-button {
  animation: upDown 1.0s 0.3s alternate;
  animation-iteration-count: 5;
}
.dots-item:nth-child(2) .dots-item-button {
  transform: translateX(100px);
}
.dots-item:nth-child(3) .dots-item-button {
  transform: translateX(200px);
  animation: rightLeft 1.0s 0.3s alternate;
  animation-iteration-count: 5;
}

.dots-item {
  display: inline-block;
}

.dots-item-button {
  width: 35px;
  height: 35px;
  background-color: #fff;
  color: #AD4C4C;
}
@-webkit-keyframes upDown {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(200px);
  }
}

@-webkit-keyframes rightLeft {
  0% {
    transform: translateX(200px);
  }
  100% {
    transform: translateX(0);
  }
}




</style>
