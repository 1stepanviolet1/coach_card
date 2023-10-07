<template>
  <div class="mx-5 my-3">
    <CoachCard />
    <CouchUsers />
  </div>
</template>

<script>

import CoachCard from './components/coach_card.vue'
import CouchUsers from './components/users.vue'

export default {
  name: 'App',
  components: {
    CoachCard,
    CouchUsers
  }
}

</script>
