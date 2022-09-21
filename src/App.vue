<template>
  <Home />
  <div id="contact">
    <Foot/>
    </div>
  
</template>

<script>
import Home from "./pages/home.vue";
import Foot from "./components/footer.vue"

export default {
  name: "App",
  components: {
    Home,
    Foot,
  },
};
</script>

<style></style>
