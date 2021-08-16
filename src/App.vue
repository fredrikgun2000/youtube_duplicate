<template>
  <div id="app">
    <Header></Header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
  import header from './components/header'

  export default {
    components: {
      'Header'  : header,
    }
  }
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  
/*
  main{
    min-height: 700px;
  }*/

  ::-webkit-scrollbar {
      width: 0px;
    }
</style>