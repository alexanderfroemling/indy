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
            list: [],
            
            
        }
    },
    mounted() {
        if (localStorage.list) {
            this.list = JSON.parse(localStorage.list);
        }
    },
    watch: {
        list: {
            handler(newList) {
            localStorage.list = JSON.stringify(newList);
            },
            deep: true
        }
    },
    methods: {
        submit: function() {
           this.list.push({...this.user})
        }
    },
}


    


</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Pirata+One|Bilbo+Swash+Caps&display=swap');

@font-face {
  font-family: Morris;
  src: url(https://cdn.statically.io/gh/EmmesCodes/Tipografias/dae9f5bb/MorrisInitials.ttf);
  }

:root {
  --fontSize: calc((1vw + 1vh) * .75);
}

.gbook {
    /*background-color: rgb(44, 44, 44);
    color: rgb(255, 255, 255);
    margin: 120px 10px;
    border: 4px solid black;
    border-radius: 20px;
    padding: 15px;*/
    font: var(--fontSize)/200% 'Bilbo Swash Caps', cursive;
    font-size: 1.5em;
    color: #7F3300;
    transform: translate(0%, 0);
    margin: auto;
    width: 80%;
    display: inline-block;
	padding: 1em 3em;
	box-shadow: 2px 3px 20px black, 0 0 125px #8f5922 inset;
	background: #fffef0;
    filter: url(#wavy2);
    background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAMAAAAp4XiDAAAAUVBMVEWFhYWDg4N3d3dtbW17e3t1dXWBgYGHh4d5eXlzc3OLi4ubm5uVlZWPj4+NjY19fX2JiYl/f39ra2uRkZGZmZlpaWmXl5dvb29xcXGTk5NnZ2c8TV1mAAAAG3RSTlNAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEAvEOwtAAAFVklEQVR4XpWWB67c2BUFb3g557T/hRo9/WUMZHlgr4Bg8Z4qQgQJlHI4A8SzFVrapvmTF9O7dmYRFZ60YiBhJRCgh1FYhiLAmdvX0CzTOpNE77ME0Zty/nWWzchDtiqrmQDeuv3powQ5ta2eN0FY0InkqDD73lT9c9lEzwUNqgFHs9VQce3TVClFCQrSTfOiYkVJQBmpbq2L6iZavPnAPcoU0dSw0SUTqz/GtrGuXfbyyBniKykOWQWGqwwMA7QiYAxi+IlPdqo+hYHnUt5ZPfnsHJyNiDtnpJyayNBkF6cWoYGAMY92U2hXHF/C1M8uP/ZtYdiuj26UdAdQQSXQErwSOMzt/XWRWAz5GuSBIkwG1H3FabJ2OsUOUhGC6tK4EMtJO0ttC6IBD3kM0ve0tJwMdSfjZo+EEISaeTr9P3wYrGjXqyC1krcKdhMpxEnt5JetoulscpyzhXN5FRpuPHvbeQaKxFAEB6EN+cYN6xD7RYGpXpNndMmZgM5Dcs3YSNFDHUo2LGfZuukSWyUYirJAdYbF3MfqEKmjM+I2EfhA94iG3L7uKrR+GdWD73ydlIB+6hgref1QTlmgmbM3/LeX5GI1Ux1RWpgxpLuZ2+I+IjzZ8wqE4nilvQdkUdfhzI5QDWy+kw5Wgg2pGpeEVeCCA7b85BO3F9DzxB3cdqvBzWcmzbyMiqhzuYqtHRVG2y4x+KOlnyqla8AoWWpuBoYRxzXrfKuILl6SfiWCbjxoZJUaCBj1CjH7GIaDbc9kqBY3W/Rgjda1iqQcOJu2WW+76pZC9QG7M00dffe9hNnseupFL53r8F7YHSwJWUKP2q+k7RdsxyOB11n0xtOvnW4irMMFNV4H0uqwS5ExsmP9AxbDTc9JwgneAT5vTiUSm1E7BSflSt3bfa1tv8Di3R8n3Af7MNWzs49hmauE2wP+ttrq+AsWpFG2awvsuOqbipWHgtuvuaAE+A1Z/7gC9hesnr+7wqCwG8c5yAg3AL1fm8T9AZtp/bbJGwl1pNrE7RuOX7PeMRUERVaPpEs+yqeoSmuOlokqw49pgomjLeh7icHNlG19yjs6XXOMedYm5xH2YxpV2tc0Ro2jJfxC50ApuxGob7lMsxfTbeUv07TyYxpeLucEH1gNd4IKH2LAg5TdVhlCafZvpskfncCfx8pOhJzd76bJWeYFnFciwcYfubRc12Ip/ppIhA1/mSZ/RxjFDrJC5xifFjJpY2Xl5zXdguFqYyTR1zSp1Y9p+tktDYYSNflcxI0iyO4TPBdlRcpeqjK/piF5bklq77VSEaA+z8qmJTFzIWiitbnzR794USKBUaT0NTEsVjZqLaFVqJoPN9ODG70IPbfBHKK+/q/AWR0tJzYHRULOa4MP+W/HfGadZUbfw177G7j/OGbIs8TahLyynl4X4RinF793Oz+BU0saXtUHrVBFT/DnA3ctNPoGbs4hRIjTok8i+algT1lTHi4SxFvONKNrgQFAq2/gFnWMXgwffgYMJpiKYkmW3tTg3ZQ9Jq+f8XN+A5eeUKHWvJWJ2sgJ1Sop+wwhqFVijqWaJhwtD8MNlSBeWNNWTa5Z5kPZw5+LbVT99wqTdx29lMUH4OIG/D86ruKEauBjvH5xy6um/Sfj7ei6UUVk4AIl3MyD4MSSTOFgSwsH/QJWaQ5as7ZcmgBZkzjjU1UrQ74ci1gWBCSGHtuV1H2mhSnO3Wp/3fEV5a+4wz//6qy8JxjZsmxxy5+4w9CDNJY09T072iKG0EnOS0arEYgXqYnXcYHwjTtUNAcMelOd4xpkoqiTYICWFq0JSiPfPDQdnt+4/wuqcXY47QILbgAAAABJRU5ErkJggg==);
    border-radius: 80px;
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
    color: white;
    letter-spacing: normal;
    word-spacing: normal;
    text-transform: none;
    text-indent: 0px;
    text-shadow: 0 0 6px black, 0 0 6px black;
    display: inline-block;
    text-align: center;
    appearance: auto;
    background-color: rgba(255,255,255,0.2);
    -webkit-rtl-ordering: logical;
    cursor: text;
    margin: 1em;
    padding: 1px 2px;
    border-width: 2px;
    border-style: inset;
    border-color: -internal-light-dark(rgb(118, 118, 118), rgb(133, 133, 133));
    border-image: initial;
    border-radius: 15px;
    font-size: 17px;
}

input::placeholder {
    color: white;
    text-shadow: 0 0 6px black, 0 0 6px black;
    font-size: 17px;
}

.btn {
    background: transparent;
    border: 3px solid white;
    padding: 10px 20px;
    font-size: 20px;
    text-shadow: 0 0 2px black, 0 0 2px black;
    margin: 20px 0px;
    color: white;
    border-radius: 30px;
    transition: opacity 200ms;
}

.btn:hover {
  color: black;
  background-color: rgb(128, 83, 0);
  opacity: 90%;
  border: white solid 3px;
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
    text-shadow: 0 0 3px black, 0 0 3px black;
}
</style>