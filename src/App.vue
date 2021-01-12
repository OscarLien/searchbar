<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="wrap">
      <h1>Search Bar</h1>
      <input type="text"  v-model="input" placeholder="Search"/>
      <ul class="list" v-for="item in filterSearch" :key="item" :value="item">
        <li>{{item}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      input: "",
      list:['Java','JavaScript', 'Python', 'Vue.js','React','Angular'],
    };
  },
  components: {
    HelloWorld,
  },
  methods: {

  },
  computed: {
    filterSearch() {
      return this.list.filter(searchResult => searchResult.toLowerCase().match(this.input));
      // return this.list;
    }

  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.wrap {
  width: 80%;
  margin: 0 auto;
  .list {
    list-style: none;
    padding: 0;
    li {
      padding: 10px 0;
    }
  }
}
</style>
