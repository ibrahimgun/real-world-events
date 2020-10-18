<template
  ><router-link
    class="event-link"
    :to="{ name: 'event-show', params: { id: event.id } }"
  >
    <div class="wrapper">
      <div class="card">
        <div class="card-banner">
          <p class="status popular">
            {{ event.status }}
          </p>
          <img class="banner-img" :src="event.bannerimg" alt="" />
        </div>
        <div class="card-body">
          <p class="time">{{ event.date }}, {{ event.time }}</p>
          <h2 class="card-title">{{ event.title }}</h2>
          <p class="card-description">{{ event.description }}</p>
          <div class="attendees">
            <BaseIcon name="users">{{ event.attendees.length }}</BaseIcon>

            <span class="location"
              ><BaseIcon name="location" />{{ event.location }}</span
            >
          </div>
        </div>
      </div>
    </div></router-link
  >
</template>

<script>
export default {
  props: {
    event: Object
  }
}
</script>

<style scoped></style>
