<script>

export default{
  data(){
    return{
      keyword: '',
      items: require("../../info.json")
    }
  },
  computed: {
    sortedItemsByDate(){
      return this.items.sort((a,b) => {
        return (a.date < b.date) ? -1 : (a.date > b.date ) ? 1 : 0
      })
    },filteredItems(){
      if(this.keyword != ''){
        var filtered_items = [];
        for(var i in this.items){
          var pre_name = this.sortedItemsByDate[i];
          if(pre_name.name.indexOf(this.keyword) !== -1){
            filtered_items.push(pre_name);
          }else if(pre_name.description.indexOf(this.keyword) !== -1){
            filtered_items.push(pre_name);
          }
        }
        return filtered_items;
      }else{
        return this.sortedItemsByDate;
      }
    }
  }
}
</script>

<template>
  <div>
    <!-- Search -->
    <div class="form-group">
      <input type="text" v-model="keyword"　placeholder="Search">
    </div>
    <div class="container">
      <div v-for="item in filteredItems" :key="item.name">
        <section>
          <h1>{{ item.date }}</h1>
          <p>{{ item.name }}</p>
          <img :src="'../../static/' + item.img" >
          <p>{{ item.description }}</p>
        </section>
      </div>
  </div>
</div>
</template>

<style>
.form-group{
  text-align: center;
}

.form-group input{
  outline: 0;
  border: 0;
}

.form-group input[type="text"]{
  width: 256px;
  padding: 8px 4px 6px 4px;
  background: #FAFAFA;
  font-size: 1.2rem;
  border-bottom: 1px solid rgba(0,0,0,.4);
}

.container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.container section{
  width: 300px;
  height: 100%;
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
