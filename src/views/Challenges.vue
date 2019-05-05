<template>
    <div>

        <ion-item>
         <ion-searchbar placeholder="Search for a Challenge"
            @ionChange="search($event)"></ion-searchbar>
        </ion-item>

        <ion-item>
           <ion-range min="1" max="3" step="1" snaps="true"
            @ionChange="levelChange($event)">
            <ion-label slot="start">Beginner</ion-label>
            <ion-label slot="end">Advanced</ion-label>
           </ion-range>
        </ion-item>

        <Card v-for="item of cards" :item="item" :key="item.id"/>
    </div>
</template>

<script>
import Card from '@/components/Card'
export default {
  name: "challenges",
  components:{
    Card
  },
  data:function(){
    return {
        searchQuery:'',
        levelSelected:"Beginner",
        items:[
          {
              title:"500 Calories Run",
              image:"/images/card-02-mod.png",
              level:"Intermediate",
              calories:500,
              points:100
          },
          {
              title:"2.4KM Run",
              image:"/images/card-01-mod.png",
              level:"Intermediate",
              calories:640,
              points:100
          },
          {
              title:"2.4KM Run",
              image:"/images/card-01-mod.png",
              level:"Intermediate",
              calories:640,
              points:100
          },
          {
              title:"1KM Run",
              image:"/images/card-01-mod.png",
              level:"Beginner",
              calories:200,
              points:50
          },
          {
              title:"5KM Run",
              image:"/images/card-01-mod.png",
              level:"Advanced",
              calories:1000,
              points:500
          }
        ],
        cards:null
    };
  },
  methods:{
      repopulateItems(){
          this.cards = this.items.filter((item)=>{
            if(this.searchQuery=='') return item.level == this.levelSelected;
            return (
                item.level == this.levelSelected
                &&
                item.title.toLowerCase()
                    .includes(this.searchQuery.toLowerCase())
            );
          });
          console.log(this.levelSelected);
          console.log(this.searchQuery);
      },
      search($event){
        this.searchQuery = $event.target.value;
        this.repopulateItems();
        //console.log($event.target.value);
      },
      levelChange($event){
        switch($event.target.value){
            case 1:
            default:
            this.levelSelected = "Beginner";
            break;
            case 2:
            this.levelSelected = "Intermediate";
            break;
            case 3:
            this.levelSelected = "Advanced";
            break;
        }
        this.repopulateItems();
        console.log(this.levelSelected);
        console.log(this.items);
      }
  },
  created(){
    this.items.forEach((item,idx)=>{
        item.id = idx;
        return item;
    });
    //this.cards = this.items;
    this.repopulateItems();
    console.log(this.cards);
  }
};

</script>
