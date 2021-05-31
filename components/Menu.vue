<template>
  
</template>

<script>

export default {
    name: 'Menu',
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


<style scoped>
.farbe {
    background-color: green;
}
</style>