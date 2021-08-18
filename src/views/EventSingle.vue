<template>
  <div class="event-single">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Event name
          </h1>
          <h2 class="subtitle ">
            Event date
          </h2>
        </div>
      </div>
    </section>
    <section class="event-content">
      <div class="container">
        <p class="is-size-4 description">Event description</p>
        <p class="is-size-4">Location:</p>
        <p class="is-size-4">Category:</p>
        <div class="event-images columns is-multiline has-text-centered">
          <div class="column is-one-third">
            IMAGE PLACEHOLDER
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
  export default {
  }
</script>
<style lang="scss" scoped>
  .event-single {
    margin-top: 30px;
  }
  .hero {
    margin-bottom: 70px;
  }
  .event-images {
    margin-top: 50px;
  }
  .description {
    margin-bottom: 30px;
  }
</style>