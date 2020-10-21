<template>
  <Header />
  <Works />
  <AboutMe />
</template>

<script>
import Header from './components/Header.vue'
import Works from './components/Works.vue'
import AboutMe from './components/AboutMe.vue'

export default {
  name: 'App',
  components: {
    Header,
    Works,
    AboutMe,
  },
}
</script>
