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
    <div class="header-cart">
        <button @click="showCart = !showCart" class="header-button">
        <h1>C</h1>
        </button>
        <span class="total-quantity">{{ totalQuantity }}</span>
        <div v-if="showCart" class="cart-dropdown">
            <ul class="cart-dropdown-list">
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
import Menu from "./Menu";
export default {
    name: 'AppHeader',
    components: {
        Menu
    },
    data() {
        return {
            products: [
                {
                    id: 1,
                    name: 'Pizza',
                    description: 'Leckere Pizza mit Oliven und Tomaten',
                    quantity: 0,
                    img: require("~/static/img/pizza.jpg"),
                },
                {
                    id: 2,
                    name: 'Curry Mix',
                    description: 'Currysorten aus aller Welt und dazu Linsen, Reis und leckere Dips',
                    quantity: 0,
                    img: require("~/static/img/curry.jpg"),
                },
                {
                    id: 3,
                    name: 'Exotische Getreidepfanne',
                    description: 'Knusprig gebratenes Getreide mit Gemüse und Kräutern und Früchten',
                    quantity: 0,
                    img: require("~/static/img/getreidepfanne.jpg"),
                },
            ],
            showCart: false
        };
    },
  
    computed: {
        cart() {
            return this.products.filter(product => product.quantity > 0);
        },
        totalQuantity() {
             return this.products.reduce(
            (total, product) => total + product.quantity,
            0
            );
        }
    },
    
    methods: {
      updateCart(product, updateType) {      
            for (let i = 0; i < this.products.length; i++) {
                if (this.products[i].id === product.id) {
                    if (updateType === 'subtract') {
                        if (this.products[i].quantity !== 0) {
                            this.products[i].quantity--;
                        }
                    } 
                    else {
                        this.products[i].quantity++;
                    }
        
                    break;
                }
            }
        }
    }

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

.header-cart {
    position: relative;
}

.header-button {
    background: none;
    border: 0;
    color: white;
    cursor: pointer;
}

i {
font-size: 2rem;
background-color: white;
min-height: 30px;
min-width: 30px;
}

.total-quantity {
align-items: center;
background: black;
border: 1px solid white;
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

.cart-dropdown-list {
    list-style: none;
} 

li {
   margin: 1rem 0;
}

</style>