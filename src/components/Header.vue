<script>
export default{
  data(){
    return{
      title: "The Birth of websites,applications",
      description: "有名なIT企業、WEBサービス、アプリーケーションの誕生日を知っていますか？"
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
