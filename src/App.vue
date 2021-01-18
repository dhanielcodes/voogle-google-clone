<template>
  <div>
    <div class="logo">
      <img alt="Vue logo" src="./assets/logo.png">
    </div>
    <HelloWorld class="main" />
    <svg width="1280" height="726" viewBox="0 0 1280 726" fill="none" xmlns="http://www.w3.org/2000/svg">
    <line x1="-336.646" y1="0.646447" x2="605.354" y2="942.646" stroke="#41B883"/>
    <line x1="-336.646" y1="102.646" x2="605.354" y2="1044.65" stroke="#41B883"/>
    <line x1="-440.646" y1="102.646" x2="501.354" y2="1044.65" stroke="#41B883"/>
    <line x1="-440.646" y1="185.646" x2="501.354" y2="1127.65" stroke="#41B883"/>
    <line x1="639.646" y1="958.146" x2="1581.65" y2="16.1464" stroke="#41B883"/>
    <line x1="741.646" y1="958.146" x2="1683.65" y2="16.1464" stroke="#41B883"/>
    <line x1="741.646" y1="1062.15" x2="1683.65" y2="120.146" stroke="#41B883"/>
    <line x1="824.646" y1="1062.15" x2="1766.65" y2="120.146" stroke="#41B883"/>
    </svg>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap');
* {
  font-family: 'Roboto', sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box
}
/* body{
  width: 90%;
  margin: auto
} */
.logo{
  width: 100%;
  text-align: center;
  margin: 90px 0;

}
svg{
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: -1;
}
.main{
  width: 90%;
  margin: auto
}
@media (max-width: 600px) {
  .logo img{
    width: 200px
  }
}
</style>
