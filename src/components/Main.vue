<template>
  <section>
    <div v-if="cards.length === 0">LOADING</div>
    <div v-else id="list">
      <Maincards
        v-for="(card, i) in filteredListDisk"
        :key="i"
        :details="card"
      />
    </div>
  </section>
</template>

<script>
// import FilterAlbum from '@/components/FilterAlbum.vue'-- prima ex
import axios from "axios";
import Maincards from "@/components/Maincards.vue";
export default {
  name: "Main",
  components: {
    Maincards
  },
  props: {
    genre: String,
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      cards: [],
    };
  },
  created() {
    this.cardMusic();
  },
  computed: {
    filteredListDisk() {
      if (this.genre === "all") {
        return this.cards;
      }
      return this.cards.filter((item) => {
        return item.genre.toLowerCase().includes(this.genre.toLowerCase());
      });
    },
  },

  methods: {
    cardMusic() {
      axios.get(this.apiUrl).then((result) => {
        this.cards = result.data.response;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section {
  width: 100%;
  height: 93vh;
  background-color: rgba(30, 45, 59, 255);
  color: white;
  #list {
    margin: auto;
    width: 60%;
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
