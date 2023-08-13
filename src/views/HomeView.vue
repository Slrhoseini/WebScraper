<template>
  <div class="home">
    <HelloWorld />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/Main-Page.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
