<template>
  <div id="app">
    <FirebaseTest></FirebaseTest>
  </div>
</template>

<script>
import FirebaseTest from './components/firebaseTest'

export default {
  name: 'app',
  components: {
    FirebaseTest
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
