<!-- <script setup lang="ts">
import { ref } from 'vue'
import type { Event } from '@/types'
import EventService from '@/services/EventService'

const event = ref<Event>()
const prop = defineProps<{ id: string }>()
const id = Number(prop.id)

EventService
  .getEvent(id)
  .then((response) => {
    event.value = response.data
  })
  .catch((error) => {
    console.error('There was an error!', error)
  })
</script>

<template>
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <nav>
      <router-link :to="{ name: 'event-detail-view', params: { id } }">Details</router-link>
      |
      <router-link :to="{ name: 'event-register-view', params: { id } }">Register</router-link>
      |
      <router-link :to="{ name: 'event-edit-view', params: { id } }">Edit</router-link>
    </nav>
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <p>{{ event.description }}</p>
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template> -->

<script setup lang="ts">
import { toRefs } from 'vue'
import type { Event } from '@/types'

const props = defineProps<{
 event: Event
 id: string
}>()

const { event } = toRefs(props)
</script>

<template>
 <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
 <p>{{ event.description }}</p>
</template>
