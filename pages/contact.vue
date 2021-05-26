<template>
  <div>
      <h2>So können Sie uns erreichen</h2>
      <div class="split"><p>
      Indy Food AG <br>
      Werner-Heisenberg-Allee 25 <br>
      80939 München <br>
      02567/132485 <br>
      </p><img src="~/static/img/indy.jpg" alt=""></div><br><br>
      <p>
      Bitte richten Sie Ihre Fragen oder Kommentare direkt an die Stelle, die der Natur 
      Ihrer Anfrage für Sie am zutrefflichsten erscheint. Seien Sie sich sicher, dass Sie uns mit ausreichen Informationen versorgen,      damit wir Ihrer Anfrage zufriedenstellend bearbeiten können. Aufgrund der aktuellen Lage kann es 
      bei der Bearbeitung zu Verzögerungen kommen, wir bitten dies zu entschuldigen. <br> <br>
      <b><em>Ihr Indy Food</em></b></p>
  </div>
</template>

<script>
export default {
    head() {
        return {
            title: "Contact Indy Food",
            meta: [
                {
                    hid: "description",
                    name: "contact",
                    content: "Abenteuer von der kulinarischen Seite",         
                 }
            ]
        }
    }
}
</script>

<style>

.split {
    display: flex;
    width: auto;
    align-items: flex-start;
    justify-content: flex-start;
}

img {
    margin-left: 10vw;
    size: 100%;
    max-height: 200px;
}
</style>