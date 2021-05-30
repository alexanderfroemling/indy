<template>
  <div>
      <h1>ÜBER UNS</h1>
      <p class="txt">Nach seinen letzten Abenteuern hat sich Herr Jones mit dem Gedanken angefreundet mit einem Restaurant seine Erlebnisse
         der letzten Jahre zu verarbeiten. Beim viele Reisen an die unterschiedlichsten Orte dieser Welt, hat er einige
         interessante kulinarische Gerichte aufgeschnappt. Die Gerichte nehmen einen jeden mit durch das Erlebte des Archäologen.
         Wir haben diese Website eingerichtet, da wir vor lauter Anfragen nicht mehr in der Lage sind die Reservierungen zu verwalten.
         Es ist auch bereits die Eröfnnung eines weiteren Restaurants am anderen Ende des Landes geplant.</p>
         <div class="eintrag">
             <div class="jahr"><strong>2012 - 2014</strong></div><div class="ereignis">Indy begann mit der Recherche für die Rezepte 
                    der Gerichte, die ihm während seinen Abenteuern Kraft und Genuss geschenkt haben.    
             </div>
         </div>
         <div class="eintrag">
             <div class="jahr"><strong>2015 - 2016</strong></div><div class="ereignis">Für seine Restaurants wollte Indy nur die besten 
                 Materialien verwenden und so machte er sich mit einem alten Freund, der ihm noch einen Gefallen schuldete, auf den Weg 
                 zu einen weit entfernten Ort. Bei seiner Heimkehr, hatte er dann alle zu benötigenden Ressourcen dabei.</div>
         </div>
         <div class="eintrag">
             <div class="jahr"><strong>2017 - 2019</strong></div><div class="ereignis">Der Rest war eine Leichtigkeit für Indy. Er 
                 versammelte uns als sein Team und gemeinsam machten wir uns an die Errichtung dieses Tempels.</div>
         </div>
         <div class="eintrag">
             <div class="jahr"><strong>2020 - Heute</strong></div><div class="ereignis">Seitdem ist es überall bekannt, dass der Name Indy 
                 für ein herausragendes Angebot an Gerichten steht, wobei das Ambiente die Kirsche auf der Torte bildet.
             </div>
         </div>
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
    margin: 2vh 1vw;
}

.eintrag {
    display: flex;
    margin-top: 40px;
    justify-content: center;
}

.jahr {
    flex: 1;
    justify-items: center;
    align-items: center;
}

.ereignis {
    flex: 2;
    font-family: serif;
}

.txt {
    margin-bottom: 20px;
}

strong {
    border: 0px solid white;
    border-radius: 20px;
    padding: 10px;
    font-size: 20px;
    background-color: rgb(48, 48, 48);
}
</style>