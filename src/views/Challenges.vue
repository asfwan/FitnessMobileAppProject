<template>
    <div>

        <ion-item>
         <ion-searchbar placeholder="Search for a Challenge"
            @ion-change="search()" v-on:click="search()"></ion-searchbar>
        </ion-item>

        <ion-item>
           <ion-range ref="rangeDualKnobs" dual-knobs="true" min="1" max="3" step="1" snaps="true">
            <ion-label slot="start">Beginner</ion-label>
            <ion-label slot="end">Advanced</ion-label>
           </ion-range>
        </ion-item>

        <ion-toolbar>
    <ion-buttons slot="secondary">
      <ion-button>
        <ion-icon slot="icon-only" name="contact"></ion-icon>
      </ion-button>
      <ion-button>
        <ion-icon slot="icon-only" name="search"></ion-icon>
      </ion-button>
    </ion-buttons>
    <ion-title>Default Buttons</ion-title>
    <ion-buttons slot="primary">
      <ion-button color="secondary">
        <ion-icon slot="icon-only" name="more"></ion-icon>
      </ion-button>
    </ion-buttons>
  </ion-toolbar>

        <Card v-for="item of items" :item="item" :key="item.id"/>
    </div>
</template>

<script>
import Card from '@/components/Card'
export default {
  name: "challenges",
  components:{
    Card
  },
  data(){
    return {
        items:[
            {
                id:1,
                title:"500 Calories Run",
                image:"/images/card-02-mod.png",
                level:"Intermediate",
                calories:500,
                points:100
            },
            {
                id:2,
                title:"2.4KM Run",
                image:"/images/card-01-mod.png",
                level:"Intermediate",
                calories:640,
                points:100
            },
            {
                id:3,
                title:"2.4KM Run",
                image:"/images/card-01-mod.png",
                level:"Intermediate",
                calories:640,
                points:100
            }
        ]
    };
  },
  methods:{
      search:()=>{
        this.console.log('test')
      }
  }
};

</script>
