<template>
  <div class="container">
    <AppHeader />
    <Nuxt />
    
  </div>
</template>
<script>
import Menu from '~/components/Menu.vue'
import AppHeader from '~/components/AppHeader.vue'
export default {  
  components: {
    Menu,AppHeader
  }
}
</script>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
 background-color: #010011;
  opacity: 1;
  background-image:  repeating-radial-gradient( circle at 0 0, transparent 0, #010011 40px ), repeating-linear-gradient( #92612f55, #92612f );
}

h1 {
  text-align: center;
  margin: 15px 0px;
}

h2 {
  text-align: left;
  margin-bottom: 20px;
}


ul {
  list-style: none;
}



.container {
  max-width: 80%;
  min-height: 100vh;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: rgb(19, 19, 19);
  color: white;
  border: white solid 1px;
}


/**,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}*/
</style>
