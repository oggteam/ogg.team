<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="less">
  @font-face {
      font-family: 'poppinssemibold';
      src: url('../static/fonts/poppins-semibold-webfont.eot');
      src: url('../static/fonts/poppins-semibold-webfont.eot?#iefix') format('embedded-opentype'),
            url('../static/fonts/poppins-semibold-webfont.woff2') format('woff2'),
            url('../static/fonts/poppins-semibold-webfont.woff') format('woff'),
            url('../static/fonts/poppins-semibold-webfont.svg#poppinssemibold') format('svg');
      font-weight: normal;
      font-style: normal;
  }
  html {
    height: 100%;
    width: 100%;
  }
  @media (max-width: 767px) {
    html {
      font-size: 12px;
    }
  }
  body {
    align-content: center;
    align-items: center;
    background-color: #000;
    box-sizing: border-box;
    color: #fff;
    display: flex;
    flex-direction: column;
    font-family: 'poppinssemibold', sans-serif;
    height: 100%;
    justify-content: center;
    margin: 0;
    padding: 0;
    width: 100%;
  }
  h1 {
    font-size: 5rem;
    margin: 0 0 4rem;
  }
  a {
    color: #fff;
    text-decoration: underline;
  }
  #app {
    height: 100%;
    width: 100%;
  }
.btn {
  background-color: transparent;
  border-radius: 6px;
  padding: 20px 40px;
  text-decoration: none;
}
.btn_skip {
  border: 1px solid #fff3;
  color: #fff3;
  outline: none;
  padding: 6px 20px;
  position: absolute;
  right: 20px;
  top: 37px;
  transition: 0.15s;
  z-index: 1;
  &:hover {
    background-color: #fff;
    border-color: #fff;
    cursor: pointer;
    color: #000;
  }
  &:active {
    background-image: linear-gradient( to bottom right,rgba(63,81,181,1) 0%, rgba(171,71,188 ,1) 70%);
    border-color: rgb(93, 41, 214);
    color: #fff;
  }
}
.btn_violet {
  background-image: linear-gradient( to bottom right,rgba(63,81,181,1) 0%, rgba(171,71,188 ,1) 70%);
  box-shadow: 1px 1px 30px rgb(93, 41, 214);
  display: inline-block;
  position: relative;
  text-transform: uppercase;
  z-index: 1;
  &:before {
    background-image: linear-gradient( to bottom right, rgba(171,71,188 ,1) 0%, rgba(63,81,181,1) 70%);
    border-radius: inherit;
    content: '';
    display: block;
    height: 100%;
    left: 0;
    opacity: 0;
    position: absolute;
    top: 0;
    transition: opacity 0.45s;
    width: 100%;
    z-index: -1;
  }
  &:hover {
    &:before {
      opacity: 1;
    }
  }
}
</style>
