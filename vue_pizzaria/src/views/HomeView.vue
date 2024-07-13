<template>
  <div>
  <Banner />
  <div class="main-container">
    <h1>Monte a sua Pizza</h1>
    <PizzForm />
  </div>
</div>
</template>

<script>
import Banner from '../components/Banner.vue'
import PizzForm from '../components/PizzForm.vue'

export default {
  name: "Home",
  components: {
    Banner,
    PizzForm
  }
}

</script>
