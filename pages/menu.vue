<template>
  <div>

    <section class="products">
        <div v-for="product in products" :key="product.id" class="product">
            <h3 class="product-header">{{ product.name }}</h3>
            <img 
            :key="product.img" 
            :src="product.img" class="product-image"
            >
            <p class="product-description">{{ product.description }}</p>
            <div class="cart">
                <button
                @click="updateCart(product, 'subtract')"
                class="cart-button"
                >
                -
                </button>
                <span class="cart-quantity">{{ product.quantity }}</span>
                <button
                @click="updateCart(product, 'add')"
                class="cart-button"
                >
                +
                </button>
            </div>
        </div>
    </section>
  </div>
</template>

<script>
export default {
    name: "menu",
    head() {
        return {
            title: "Menu Indy Food",
            meta: [
                {
                    hid: "description",
                    name: "menu",
                    content: "Abenteuer von der kulinarischen Seite",         
                 }
            ]
        }
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

.products {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
} 
  
.product {
    border: 1px solid lightgray;
    border-radius: 10px;
    margin: 2rem;
    padding: 1rem;
}

.product-header {
      font-size: 2rem;
      text-align: center;
}

.product-image {
        display: block;
        margin: 1rem auto;
}

.product-description {
        font-size: 1.3rem;
        margin-top: 1rem;
}

.cart {
  margin-top: 2rem;
  text-align: center;
}

.cart-button {
    background: lightblue;
    border: 0;
    color: white;
    cursor: pointer;
    font-size: 1.5rem;
    font-weight: bold;
    height: 2.5rem;
    width: 2.5rem;
}
  
.cart-quantity {
    font-size: 1.5rem;
    margin: 0 1rem;
}

</style>