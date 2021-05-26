<template>
  <div class="guest">
      <h4>Gästebuch</h4>
      <input class="inputname" type="text" placeholder="Name" v-model="user.name">
      <input class="inputmessage" type="text" placeholder="Wie hat es Ihnen gefallen?" v-model="user.message">
      <button class="btn" @click="submit">Verewigen</button>
      <ul class="gbook">
        <li v-for="user in list" :key="user.name">
            {{ user.name + ':' + ' ' + '"' + user.message + '"' }}<br><br><br>
        </li>
        
        </ul>
      
  </div>
</template>

<script>
export default {
    head() {
        return {
            title: "Guestbook Indy Food",
            meta: [
                {
                    hid: "description",
                    name: "guestbook",
                    content: "Abenteuer von der kulinarischen Seite",         
                 }
            ]
        }
     },
     data() {
        return {
            user: {
                name: '',
                message: '',

            },
            list: []
            
        }
    },
    methods: {
        submit: function() {
           console.log(this.user)
           this.list.push({...this.user})
           console.log(this.list)
        }
    },
}


    


</script>

<style>


.gbook {
    background-color: rgb(44, 44, 44);
    color: rgb(255, 255, 255);
    margin: 120px 10px;
    border: 4px solid black;
    border-radius: 20px;
    padding: 15px;
}

.inputname {
    height: 2vh;
    width: 50%;
}


.inputmessage{
    height: 8vh;
    width: 50%;
}

input {
    text-rendering: auto;
    color: -internal-light-dark(black, white);
    letter-spacing: normal;
    word-spacing: normal;
    text-transform: none;
    text-indent: 0px;
    text-shadow: none;
    display: inline-block;
    text-align: center;
    appearance: auto;
    background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
    -webkit-rtl-ordering: logical;
    cursor: text;
    margin: 1em;
    font: 400 13.3333px Arial;
    padding: 1px 2px;
    border-width: 2px;
    border-style: inset;
    border-color: -internal-light-dark(rgb(118, 118, 118), rgb(133, 133, 133));
    border-image: initial;
    border-radius: 15px;
}

.btn {
    background: blue;
    border: 2px solid white;
    padding: 10px 20px;
    margin: 20px 0px;
    color: white;
    border-radius: 20px;
    transition: opacity 200ms;
}

.btn:hover {
  color: black;
  background-color: rgb(0, 183, 255);
  opacity: 90%;
  border: white solid 2px;
}

.guest {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-image: url('~/static/img/book.jpg');
    background-repeat: no-repeat;
    background-size: 100%;
}

h4 {
    text-align: center;
    align-content: center;
    color: white;
    font-size: 250%;
    margin: 20px 0px;
    border: 3px solid white;
    border-radius: 10px;
    padding: 0px 10px;
}
</style>