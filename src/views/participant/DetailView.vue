<!-- <script setup lang="ts">
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
</template> -->

<script setup lang="ts">
import { toRefs } from 'vue'
import type { Participant } from '@/types'

const props = defineProps<{
  participant: Participant
  id: string
}>()

const { participant } = toRefs(props)
</script>

<template>
  <h2>{{ participant.name }}</h2>
  <p>{{ participant.email }}</p>
</template>
