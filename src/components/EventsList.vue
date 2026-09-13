<template>
  <div class="events container">
    <h2 class="subtitle is-3">
    Check out our upcoming events
    </h2>
    <div class="columns is-multiline">
      <div v-for="event in events" :event="event" :key="event.id" class="column is-one-quarter">
        <router-link :to="'/event/' + event.id">
          <EventCard :event="event" />
        </router-link>
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
  },
  data () {
    return {
      event: {},
      events: [
        {
          id: 1,
          name: 'Beowulf Reading',
          category: 'Culture',
          description: 'Spend an elegant night of dinner and storytelling. Readings by Vilkas the Viking.',
          featuredImage: '/helmets400x267.jpg',
          images: [
            '/helmets400x267.jpg'
          ],
          location: '1111 Norse Ave',
          date: '9-25-2021',
          time: '7:30'
        },
        {
          id: 2,
          name: 'Shield Recycling',
          category: 'Charity and Donations',
          description: 'Come to our donation drive to help us replenish shields.  Enjoy an afternoon of games, food, music and much more.',
          featuredImage: '/helmets400x267.jpg',
          images: [
            '/helmets400x267.jpg'
          ],
          location: '123 Runestone Way',
          date: '11-21-2021',
          time: '12:00'
        }
      ]
    }    
  }
}

</script>
<style lang="scss" scoped>
  .events {
    margin-top: 100px;
    text-align: center;
  }
</style>
<!-- This will create a block of cards that takes up 1/4 of the row (by using Bulma's column with is-one-quarter). Each of those 1/4 slots will be filled with the EventCard component.

🛠️️ For now, just repeat that card code a couple of times so that you can see how the structure will look.

<div class="columns is-multiline">
  <div class="column is-one-quarter">
    <EventCard />
  </div>
  <div class="column is-one-quarter">
    <EventCard />
  </div>
</div> -->