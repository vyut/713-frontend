<script setup lang="ts">
import { useParticipantStore } from '@/stores/participant'
import { storeToRefs } from 'pinia'
const store = useParticipantStore()
const { participant } = storeToRefs(store)

const props = defineProps<{ id: string }>()
const id = Number(props.id)
</script>

<template>
  <div v-if="participant">
    <h1>{{ participant.name }}</h1>
    <nav>
      <router-link :to="{ name: 'participant-detail-view', params: { id } }">Details</router-link>
      |
      <router-link :to="{ name: 'participant-edit-view', params: { id } }">Edit</router-link>
    </nav>
    <router-view :participant="participant" :id="id" />
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>
