<template>
  <div id="app">
    <HelloWorld />
    <SampleTable />
    <addData />
  </div>
</template>

<script>
import SampleTable from './components/SampleTable.vue';
import HelloWorld from './components/HelloWorld.vue';
import addData from './components/addData.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    SampleTable,
    addData
  },
  data() {
    return {}
  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(35, 70, 230);
  /* background-color: rgb(249, 252, 255); */
  /* margin-top: 60px; */
}
</style>
