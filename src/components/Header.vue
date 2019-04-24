<script>
export default{
  data(){
    return{
      title: "The Birth of websites,applications",
      description: "Googleをはじめ、有名なIT企業、WEBサービス、アプリーケーションがいつできたかを知っていますか？"
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
