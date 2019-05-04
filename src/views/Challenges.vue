<template>
  <div class="about">
      
  </div>
</template>

<script>
import { Component, Vue } from 'vue';
@Component()
  export default class MenuExample extends Vue {
    openFirst() {
      this.menu.enable(true, 'first');
      this.menu.open('first');
    }
  }
</script>
