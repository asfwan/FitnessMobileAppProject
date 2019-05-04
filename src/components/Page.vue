<template>
  <div class="ion-page">
    <ion-header>
        <ion-toolbar>
            <ion-title>{{header_title}}</ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding" :scrollEvents="true">
        <slot/>
    </ion-content>
  </div>
</template>

<script>
export default {
  name: "page",
  props: ['header_title']
};
</script>
