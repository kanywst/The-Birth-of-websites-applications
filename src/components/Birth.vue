<script>
//const results = require("../../info.json")

export default{
  data(){
    return{
      items: require("../../info.json")
    }
  },
  computed: {
    sortedItemsByDate(){
      return this.items.sort((a,b) => {
        return (a.date < b.date) ? -1 : (a.date > b.date ) ? 1 : 0
      })
    }
  }
}
</script>

<template>
  <div class="container">
      <div v-for="item in sortedItemsByDate" :key="item.name">
        <section>
          <h1>{{ item.date }}</h1>
          <p>{{ item.name }}</p>
          <img :src="'../../static/' + item.img" >
          <p>{{ item.description }}</p>
          <!-- <span>{{ item.type }}</span> -->
        </section>
      </div>
  </div>
</template>

<style>
.container{
  display: flex;
  flex-wrap: wrap;
  /*justify-content: space-between;*/
  justify-content: center;
  /*align-items: center;*/
}

.container section{
  width: 300px;
  margin: 10px;
  padding: 15px;
}

.container section img{
  height: 50px;
  width: auto;
  max-width: 100%;
}

.container h1{
  font-size: 1.5rem;
}

.container p{
  margin-top: 10px;
}
</style>
