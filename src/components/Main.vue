<template>
      <section>
          <div v-if="cards.length===0">LOADINDG</div>
          <div v-else id="list">
          <Maincards
          v-for="card, i in cards"
          :key="i"
          :details="card"/>
      </div>
      </section>
</template>

<script>
import axios from "axios";
import Maincards from "@/components/Maincards.vue";
export default {
  name: "Main",
  components: {
      Maincards,
  },
 data() {
      return{
          apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
          cards: [], 
        }
},
created(){
    this.cardMusic();
},

methods:{
   cardMusic() {
       axios
       .get(this.apiUrl)
       .then((result) => {
           this.cards = result.data.response;

        })
    }
}
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section {
    width: 100%;
    height:93vh;
    background-color:rgba(30,45,59,255);
    color: white;
    #list{
        margin: auto;
        width: 60%;
        display: flex;
        flex-wrap: wrap;
    }
}
</style>
