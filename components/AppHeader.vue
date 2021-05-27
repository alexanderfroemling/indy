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
    <div class="header_cart">
        <button @click="showCart = !showCart">
        <i class="fas fa-shopping-cart"></i>
        </button>
        <span class="total-quantity">{{ totalQuantity }}</span>
        <div v-if="showCart" class="cart-dropdown">
            <ul class="cart-dropdown__list">
                <li
                v-for="product in cart"
                :key="product.id"
                >
                {{ product.name }} ({{ product.quantity}})
                </li>
            </ul>
        </div>
    </div> 
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

.headercart {
    position: relative;
}

button {
    background: none;
    border: 0;
    color: white;
    cursor: pointer;
}

i {
font-size: 2rem;
}

.total-quantity {
align-items: center;
background: lightblue;
border-radius: 50%;
display: flex;
font-weight: bold;
height: 2rem;
justify-content: center;
padding: 0.5rem;
position: absolute;
right: -10px;
top: -10px;
width: 2rem;
}

.cart-dropdown {
background: white;
border: 1px solid lightgray;
border-radius: 10px;
box-shadow: 0 0 2px rgba(0, 0, 0, 0.2);
color: #333;
font-size: 1.3rem;
overflow: auto;
padding: 0 1rem;
position: absolute;
right: 0;
width: 12rem;
}

.cart-dropdown__list {
    list-style: none;
} 

li {
   margin: 1rem 0;
}

</style>