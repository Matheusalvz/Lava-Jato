<template>
  <Banner />
  <div class="main-container">
    <h1>Insira as informações</h1>
    <CarForm />
  </div>
</template>

<script>
import Banner from '../components/Banner.vue';
import CarForm from '../components/CarForm.vue'

export default{
  name: "Home",
  components: {
    Banner,
    CarForm,
  }
}
</script>
