<template>
  <div>
   <Navbar :logo="logo_src" :alt="app_name"/>
   <router-view/>
   <Footer />
</div>
</template>


<script>
import Navbar from  './components/Navbar.vue';
import Footer from './components/Footer.vue';


export default {
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      logo_src: "/img/pizza.png",
      app_name: "Make Your Pizza"
    }
  }
}
</script>


<style>
  * {
    font-family: Helvetica;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  .main-container {
    margin: 50px;
    min-height: 400px;
  }

  h1 {
    text-align: center;
    font-size: 58px;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    margin-bottom: 30px;
    color: #E6531D;
  }
</style>
