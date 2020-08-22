<template>
  <div class="details">
    <Single />
  </div>
</template>

<script>
// @ is an alias to /src
import Single from '@/components/Single.vue'

export default {
  name: 'Details',
  components: {
    Single
  }
}
</script>