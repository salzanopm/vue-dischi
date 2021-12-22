<template>
  <div id="app">
    <Header />
    <main>
      <CardlList />
    </main>
    
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CardlList from "./components/CardList.vue";

export default {
  name: "App",
  components: {
    Header,
    CardlList
  },
};
</script>

<style lang="scss">
@import './style/general.scss';
</style>
