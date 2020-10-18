<template>
  <div class="page">
    <div class="pageHead">
      <p class="date-info">{{ event.date }}</p>
      <h1>{{ event.title }}</h1>
      <span>Hosted by {{ event.organizer }} </span>
    </div>
    <div class="pageBody">
      <div class="page-details">
        <div class="event-detail">
          <h3>Details</h3>
          <p>
            Lorem Ipsum is simply dummy text of the printing and typesetting
            industry. Lorem Ipsum has been the industry's standard dummy text
            ever since the 1500s, when an unknown printer took a galley of type
            and scrambled it to make a type specimen book. It has survived not
            only five centuries.
          </p>
        </div>
        <div class="category-info">
          <p>
            <BaseIcon name="folder">{{ event.category }}</BaseIcon>
          </p>
          <p>
            <BaseIcon name="clock">{{ event.time }}</BaseIcon>
          </p>
          <p>
            <BaseIcon name="calendar">{{ event.date }}</BaseIcon>
          </p>
          <p>
            <BaseIcon name="monitor">{{ event.status }}</BaseIcon>
          </p>
          <p>
            <BaseIcon name="location">{{ event.location }}</BaseIcon>
          </p>
        </div>
      </div>
      <div class="page-att">
        <h3>Attendees ({{ event.attendees ? event.attendees.length : 0 }})</h3>
        <li
          v-for="(attendee, index) in event.attendees"
          :key="index"
          class="list-item"
        >
          {{ attendee.name }}
        </li>
      </div>
    </div>
  </div>
</template>
<script>
import EventService from '@/services/EventService.js'
export default {
  props: ['id'],
  data() {
    return {
      event: {}
    }
  },
  created() {
    EventService.getEvent(this.id)
      .then(response => {
        this.event = response.data
      })
      .catch(error => {
        console.log('There was an error:', error.response)
      })
  }
}
</script>
<style scoped>
.pageHead {
  margin-left: 24rem;
}
.pageBody {
}
.page-details {
  display: flex;
}
.event-detail {
  margin-right: 16rem;
  margin-left: 24rem;
  margin-top: 2rem;
}
.category-info {
  border-radius: 8px;
  min-width: 400px;
  margin-right: 8rem;
  margin-top: 2rem;
  margin-bottom: 2rem;
}
.page-att {
  margin-right: 16rem;
  margin-left: 24rem;
  margin-top: 2rem;
}
</style>
