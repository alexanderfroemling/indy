<template>
 <div>
  <header class="header">
      <h1 class="title">Indy Food</h1>
      <ul>
          <li>
              <nuxt-link to='/'>HOME</nuxt-link>
              <nuxt-link to='/menu'>MENU</nuxt-link>
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
     border-bottom: 1px dotted #ccc;
 }

 .header .title {
     font-size: 3rem;
     color: #526488;
 }

 .header_ul {
     display: flex;
 }

 .header_a {
     display: inline-block;
     background: #fff;
     padding: 0,3rem 1rem;
     margin-right: 0,5rem;
 }
</style>