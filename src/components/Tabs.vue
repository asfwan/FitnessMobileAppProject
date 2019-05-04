<template>
    <ion-tabs>
      <slot/>
      <ion-tab tab="/"></ion-tab>
      <ion-tab tab="/timeline"></ion-tab>
      <ion-tab tab="/nearby"></ion-tab>
      <ion-tab tab="/challenges"></ion-tab>

      <ion-tab-bar slot="bottom">

        <ion-tab-button tab="/">
          <ion-img src="/images/ic-toolbar-db-d.png" name="dashboard"></ion-img>
          <ion-label>Dashboard</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="/timeline">
          <ion-img src="/images/ic-toolbar-timeline-d.png" name="timeline"></ion-img>
          <ion-label>Timeline</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="/nearby">
          <ion-icon name="pin"></ion-icon>
          <ion-label>Nearby</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="/challenges">
          <ion-img src="/images/ic-toolbar-challenges-d.png" name="challenges"></ion-img>
          <ion-label>Challenges</ion-label>
        </ion-tab-button>

      </ion-tab-bar>
    </ion-tabs>
</template>

<script>
export default {
  name: 'tabs',
}
</script>
