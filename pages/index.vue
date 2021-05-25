<template>
 <div>
   <div class="restaurant">
     <h3>Herzlich willkommen zu Ihrem kulinarischen Abenteuer!</h3>
   </div>
   <!--<img src="~/static/img/restaurant.png" class="background">-->
  <!--<div class="bar">
   <h1>Indiana Jones Restaurant</h1>
    <div class="side-left"></div>
    <nav>
      <ul class="container">
        <li><a href="#home" class="menu">HOME</a></li>
        <li><a href="#menu" class="menu">MENÜ</a></li>
        <li><a href="#about" class="menu">ÜBER UNS</a></li>
        <li><a href="#contact" class="menu">KONTAKT</a></li>
      </ul>
    </nav>
    <div class="side-right"></div>
  </div>-->
 </div>
</template>

<script>
export default {
  head() {
        return {
            title: "Indy Food",
            meta: [
                {
                    hid: "description",
                    name: "home",
                    content: "Abenteuer von der kulinarischen Seite",
                }
            ]
        }
    }
}
</script>

<style>
.restaurant {
  background-image: url('~/static/img/restaurant.png');
  width: 76.9vw;
  height: 86vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.restaurant h3 {
  font-size: 50px;
  color: antiquewhite;
  text-align: center;
}

</style>
