<template>
  <div class="events container">
    <h2 class="subtitle is-3">
    Check out our upcoming events
    </h2>
    <div class="columns is-multiline">
      <div class="column is-one-quarter">
          <EventCard />
      </div>
      <div class="column is-one-quarter">
          <EventCard />
      </div>
      <div class="column is-one-quarter">
          <EventCard />
      </div>
      <div class="column is-one-quarter">
          <EventCard />
      </div>
      <div class="column is-one-quarter">
          <EventCard />
      </div>
    </div>
  </div>
</template>
<script>
  import EventCard from '@/components/EventCard';
  export default {
    name: 'EventsList',
    components : {
      EventCard
    }
  }
</script>
<style lang="scss" scoped>
  .events {
    margin-top: 100px;
    text-align: center;
  }
</style>