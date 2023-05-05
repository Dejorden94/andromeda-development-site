<template>
  <article class="about">
    <section>
      <h2>About Dejorden Moerman</h2>
      <img src="../../img/jpg/Dejorden.JPG" alt="The man, the myth, the legend, Dejorden Moerman.">
    </section>
  </article>
</template>

<script>

export default {

}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
  }

  .about>section {
    height: 60vh;
  }

  .about>section>img {
    height: 100%;
  }
}
</style>
