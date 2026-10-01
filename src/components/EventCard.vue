<template>
<div class="event-card">
    <div class="card">
      <div class="card-content">
        <h2 class="is-size-4 has-text-weight-bold">{{ event.name }}</h2>
        <small class="event-date">{{ formattedEventDate }}</small>  
        <span>{{ event.location }}</span>
      </div>
    </div>
  </div>
</template>
<script>
import dayjs from 'dayjs'

export default {
  props: [
    'event'
  ],
  computed: {
    formattedEventDate() {
      const date = this.event.date

      if (!date) return 'Date to be announced'

      const parsedDate = dayjs(date)

      return parsedDate.isValid()
        ? parsedDate.format('MMMM D, YYYY')
        : date
    }
  }
}
</script>

<style lang="scss" scoped>
  .card {
    background-image: url('/helmets400x267.jpg');
    height: 200px;
    background-position: center;
    background-size: cover;
    text-align: center;
  }
  .card-content {
    padding-top: 50px;
    position: absolute;
    color: #FFF;
    background-color: rgba(0, 0, 0, 0.35);
    top: 0;
    padding: 10px;
    height: 200px;
    width: 100%;
    span {
      font-size: 18px;
      text-align: center;
      width: 100%;
      position: absolute;
      bottom: 10px;
      right: 0;
    }
    h2 {
      margin-top: 10px;
    }
  }
  .event-date {
    background-color: #151515;
    color: #FFF;
    font-size: .75em;
    padding: 2px 10px;
    position: absolute;
    top: 0;
    right: 0;
  }
</style>
