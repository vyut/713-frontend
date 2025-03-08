<script setup lang="ts">
import { ref } from 'vue'
import EventCard from '@/components/EventCard.vue'

const events = ref([
  {
    id: 1,
    category: 'Category 1',
    title: 'Event 1 - Vue.js',
    description: 'Vue.js Meetup',
    date: '2021-10-10',
    time: '10:00',
    location: 'Location 1',
    petsAllowed: true,
    organizer: {
      name: 'Organizer 1',
    },
  },
  {
    id: 2,
    category: 'Category 2',
    title: 'Event 2 - React',
    description: 'React Meetup',
    date: '2021-10-11',
    time: '11:00',
    location: 'Location 2',
    petsAllowed: false,
    organizer: {
      name: 'Organizer 2',
    },
  },
  {
    id: 3,
    category: 'Category 3',
    title: 'Event 3 - Angular',
    description: 'Angular Meetup',
    date: '2021-10-12',
    time: '12:00',
    location: 'Location 3',
    petsAllowed: true,
    organizer: {
      name: 'Organizer 3',
    },
  },
])
</script>

<template>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
