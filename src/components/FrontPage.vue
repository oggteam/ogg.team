<template>
  <div class="wrapper">
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
    <div class="slide slide_6">
      <h1>under construction</h1>
      <a class="btn btn_violet" href="mailto:info@ogg.team">Work together</a>
      <div class="collapse navbar-collapse">
        <ul class="nav">
          <li class="nav_item">
            <a class="nav_item_link" target="_blank" href="https://www.behance.net/oggteam">Portfolio</a>
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
  },
}
</script>


<style lang="less">
.wrapper {
  height: 100%;
  width: 100%;
  text-align: center;
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
  width: 100%;
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
// Dots
// *****
.dots {
  filter: url("#goo");
  left: calc(50% - 32px);
  position: absolute;
  top: 35px;
}
.dots__item {
  background-color: #fff;
  border-radius: 50%;
  height: 15px;
  left: 0;
  position: absolute;
  top: 0;
  width: 15px;
}
.dots__item_center {
  transform: translateX(25px);
}
.dots__item_last {
  transform: translateX(50px);
}
</style>
