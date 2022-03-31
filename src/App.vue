<template>
  <div id="app">
    <div>{{ user.name | toUpperCase }}</div>
    <div>{{ nameOfUser }}</div>
    <button @click="increaseNumber()">Tang</button>
    <button @click="decreaseNumber()">Giam</button>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  components: {},
  data() {
    return {
      image: 'https://cdn.vjshop.vn/hightech/may-choi-game/ps5/sony-ps-5-1.jpg',
      imageAlt: 'ps5 alt',
      product: 'ps5',
      productLink: 'https://bachtungps.com.vn/may-sony-playstation-5-ps5-1',
      quantity: 10,
      price: 10000,
      discount: 0.2,
      inStock: true,
      classObject: {
        'bg-green': true,
        'bg-blue': false
      }
    }
  },
  methods: {
    increaseNumber() {
      this.numberCounter++;
    },
    decreaseNumber() {
      this.numberCounter--;
    },
  },
  computed: {
    nameOfUser() {
      const { name } = this.user;
      return name;
    },
  },
  watch: {
    numberCounter(newValue, oldValue) {
      console.log(newValue, oldValue);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
