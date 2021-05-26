<template>
 <div>
  <header class="header">
      <h1 class="title">Indy Food</h1>
      <ul>
          <li>
              <nuxt-link to='/'>HOME</nuxt-link>
              <nuxt-link to='/menu'>MENU</nuxt-link>
              <nuxt-link to='/guestbook'>GÄSTEBUCH</nuxt-link>
              <nuxt-link to='/about'>ABOUT</nuxt-link>
              <nuxt-link to='/contact'>KONTAKT</nuxt-link>
          </li>
      </ul>
  </header>
 </div>
  
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style>
 .header {
     display: flex;
     justify-content: space-between;
     align-items: center;
     margin-bottom: 1rem;
     padding-bottom: 1rem;
     border-bottom: 1px solid #ccc;
 }

 .header .title {
     font-size: 55px;
     color: white;
 }

 .header ul {
     display: flex;
 }

 .header a {
     display: inline-block;
     margin: 5px 4px;
     color: rgb(255, 255, 255);
     text-decoration: none;
     background-color: rgb(70, 70, 70);
     border: darkgray solid 3px;
     padding: 2px 5px;
     transition: opacity 200ms;
     border-radius: 20px;
 }

.header a:hover {
  color: black;
  background-color: rgb(0, 183, 255);
  opacity: 90%;
  border: white solid 3px;
}

</style>