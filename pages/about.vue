<template>
  <div>
      <h1>ÜBER UNS</h1>
      <p>Nach seinen letzten Abenteuern hat sich Herr Jones mit dem Gedanken angefreundet mit einem Restaurant seine Erlebnisse
         der letzten Jahre zu verarbeiten. Beim viele Reisen an die unterschiedlichsten Orte dieser Welt, hat er einige
         interessante kulinarische Gerichte aufgeschnappt. Die Gerichte nehmen einen jeden mit durch das Erlebte des Archäologen
         Wir haben diese Website eingerichtet, da wir vor lauter Anfragen nicht mehr in der Lage sind die Reservierungen zu verwalten.
         Es ist auch bereits die Eröfnnung eines weiteren Restaurants am anderen Ende des Landes geplant.</p>
         <div class="sunset"></div>
  </div>
</template>

<script>
export default {
    head() {
        return {
            title: "About Indy Food",
            meta: [
                {
                    hid: "description",
                    name: "about",
                    content: "Abenteuer von der kulinarischen Seite",
                }
            ]
        }
    }
}
</script>

<style>

.sunset {
    background-image: url('~/static/img/indysunset.png');
    min-height: 1000px;
    background-repeat: no-repeat;
    background-size: 100%;
    margin: 3vh 1vw;
}

</style>