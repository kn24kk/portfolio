<template>
  <header class="header">
    <h1 class="title">Portfolio</h1>
    <p class="subtitle">神津薫</p>
    <ul class="nav">
      <li><a href="#works">Works</a></li>
      <li><a href="#aboutme">About Me</a></li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
  },
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>

@import '../ver.scss';

.header {
  padding: 20vh 0;
  position: relative;
  text-align: center;
  background: #fff;
}
.title {
  color: $gray;
  font-size: 3em;
  font-family: $sans-serif-en;
}
.subtitle {
  margin-bottom: 2em;
}
.nav {
  margin: 0 auto;
  list-style: none;
  margin: 0;
  padding: 0;
  font-family: $sans-serif-en;
  li {
    display: inline-block;
    margin: 0 1em;
    padding: 0;
    a {
      color: $black;
      text-decoration: none;
      border-bottom: 1px solid $l-gray;
      transition: .3s ease-in-out;
      &:hover {
        border-color: $accent;
        letter-spacing: .2em;
      }
    }
  }
}
</style>