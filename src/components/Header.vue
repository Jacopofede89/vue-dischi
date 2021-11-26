<template>
<header>
      <section>
          <i class="fab fa-spotify"></i>
      </section>
      
  </header>
  
</template>

<script>
export default {
  name: "Header"
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
    height:7vh;
    background-color:rgba(46,58,70,255);
    display: flex;  
    align-items: center;
    section {
        width: 95%;
        margin: auto;
        i {
        color:rgba(30,215,96,255);
        font-size: 40px;
        float: left;
        }
        
    }
    
    
}
</style>
