<template>
  <div class="home">
    <Beers />
  </div>
</template>

<script>
// @ is an alias to /src
import Beers from '@/components/Beers.vue'

export default {
  name: 'Home',
  components: {
    Beers
  }
}
</script>
