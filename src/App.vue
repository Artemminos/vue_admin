<template>
  <Sidebar/>


  <div class="container">
    <Header/>

    <div class="content">
      <router-view/>

    </div>
    <footer class="footer">

    </footer>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar/Sidebar.vue';
import Header from './components/Header/Header.vue'

export default {
  name: "App",
  components: {
    Sidebar,
    Header
  },
  props: {}
};
</script>
