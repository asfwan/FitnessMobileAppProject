<template>
    <ion-card>

        <ion-img :src="item.image"></ion-img>

        <h5>{{item.title}}</h5>

        <ion-item href="#" class="activated">
          <ion-text color="danger">
            <ion-icon name="radio-button-on"></ion-icon> {{item.level}}
          </ion-text>

          <ion-text color="medium">&nbsp;|&nbsp;</ion-text>

          <ion-text color="warning"><ion-icon name="flame">
            </ion-icon> {{item.calories}} Calories
          </ion-text>

          <ion-text color="medium">&nbsp;|&nbsp;</ion-text>

          <ion-text color="primary">
            <ion-icon name="add"></ion-icon> {{item.points}} points
          </ion-text>
        </ion-item>
    </ion-card>
</template>

<script>
export default {
  name: "card",
  props:['item']
};
</script>

<style>
h5{
    text-align:left;
    padding:0px 10px;
}
ion-text{
    font-size:15px;
}
</style>
