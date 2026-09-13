<template>
  <div class="event-single">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            {{ event.name }}
          </h1>
          <h2 class="subtitle ">
            <strong>Date:</strong> {{ event.date }}
            <br>
            <strong>Time:</strong> {{ event.time }}
          </h2>
        </div>
      </div>
    </section>
    <section class="event-content">
      <div class="container">
        <p class="is-size-4 description">{{ event.description }}</p>
        <p class="is-size-5"><strong>Location:</strong> {{ event.location }}</p>
        <p class="is-size-5"><strong>Category:</strong> {{ event.category }}</p>
        <div class="event-images columns is-multiline has-text-centered">
          <div v-for="image in event.images" :key="image.id" class="column is-one-third">
            <!-- <img :src="image" :alt="event.name"> --> 
            <img :src="`${image}`" :alt="`${event.name}`" /> 
           <!--  <img :src=image :alt="event.name"> --> 

          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  name: 'EventSingle',
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
  },
  created() {
    const ID = Number(this.$route.params.id);
    let event = this.events.find(event => event.id === ID);
    this.event = event;
  }
}
</script>