<template>
    <div>
        <select v-model="lista" @change="$emit('search', lista)">
            <option :value="'all'">All</option>
            <option :value="'metal'">Metal</option>
            <option :value="'jazz'">Jazz</option>
            <option :value="'rock'">Rock</option>
            <option :value="'pop'">Pop</option>
        </select>
    </div>
</template>

<script>
export default {
  name: "FilterAlbum",
  data(){
      return{
          lista:""
      }
  }

};
</script>

<style scoped lang="scss">
  select {
    margin: auto;
    display: flex;
    justify-content: center;
    width: 10%;
    h3 {
        color: white;
        margin-right: 10px;
    }
    select option {
        background: #2e3a46;
        color: #fff;
    }
  }
</style>