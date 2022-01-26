<template>
  <div>
    <div v-if="state === 'home'">
      <h1>Hello</h1>
      <button v-on:click="changeState">Order now</button>
    </div>
    <div v-else-if="state === 'ordering'">
      <Order></Order>
    </div>
    <div v-else-if="state === 'delivery'">Delivery</div>
    <div v-else-if="state === 'confirmation'">Confirm</div>
  </div>
</template>

<script>
import Order from "./components/order.vue";

export default {
  name: "App",
  components: {
    Order
  },
  data() {
    return {
      state: "home"
    };
  },
  methods: {
    changeState() {
      this.state = "ordering";
      console.log("click");
    }
  }
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
</style>
