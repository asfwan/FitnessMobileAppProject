<template>
  <div id="app">

    <Tabs>
        <router-view/>
    </Tabs>

  </div>
</template>

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

<script>
import Tabs from './components/Tabs';
export default {
  name: 'app',
  components: {
    Tabs
  }
}
</script>
