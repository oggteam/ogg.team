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

<style>
  @font-face {
      font-family: 'poppinssemibold';
      src: url('./assets/fonts/poppins-semibold-webfont.eot');
      src: url('./assets/fonts/poppins-semibold-webfont.eot?#iefix') format('embedded-opentype'),
            url('./assets/fonts/poppins-semibold-webfont.woff2') format('woff2'),
            url('./assets/fonts/poppins-semibold-webfont.woff') format('woff'),
            url('./assets/fonts/poppins-semibold-webfont.svg#poppinssemibold') format('svg');
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
    font-family: 'poppinssemibold', sans-serif;
    align-content: center;
    align-items: center;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    margin: 0;
    padding: 0;
    width: 100%;
    background-color: #000;
    color: #fff;
  }
  h1 {
    font-size: 4rem;
    margin: 0;
  }
  a {
    color: #000;
    text-decoration: underline;
  }
  #app {
    height: 100%;
    width: 100%;
  }
</style>
