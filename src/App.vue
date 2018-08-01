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
  html {
    height: 100%;
    width: 100%;
  }
  @media (max-width: 767px) {
    html {
      font-size: 14px;
    }
  }
  body {
    align-content: center;
    align-items: center;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    font-family: 'Lato', sans-serif;
    height: 100%;
    justify-content: center;
    margin: 0;
    padding: 0;
    width: 100%;
    background-color: #000;
    color: #fff;
  }
  h1 {
    font-size: 6.250rem;
    margin: 0;
  }
  a {
    color: #000;
    text-decoration: underline;
  }
</style>
