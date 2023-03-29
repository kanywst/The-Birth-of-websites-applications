<script>
export default{
  data(){
    return{
      title: "The Birth of websites",
      description: "Do you know the birthdays of IT companies, web services, and applications?"
    }
  }
}
</script>

<template>
  <header>
    <h1>{{ title }}</h1>
    <p>{{ description }}</p>
  </header>
</template>

<style>
header{
  text-align: center;
}
</style>
