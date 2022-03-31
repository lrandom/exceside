<template>
  <div>
    <div >
      <div class="modal" :class="{ hidden: !inStrock }" >
        <img :src="imgModal" alt="photo">
        <button @click="toggleModal">X</button>
      </div>
      <div v-for="img in listImg" :key="img.id">
        <img :src="img.img" alt="photo" @click="toggleModal(img.img)" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imgModal : '',
      listImg: [
        { img: require("./assets/girl-1.jpg") },
        { img: require("./assets/logo.png") },
      ],
      inStrock: false,
    };
  },
  methods: {
    toggleModal(src) {
      this.inStrock = !this.inStrock;
      this.imgModal = src;
    },
    test() {
      console.log("test");
    }
  },
  moutend:function() {
    document.addEventListener('keydown', (e) => {
      if (e.key === "Escape") {
        this.test();
      }
    });
  }
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
.hidden {
  display: none !important;
}
.modal {
  background: rgb(14, 14, 14, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}
.modal img {
  width: 400px;
  height: 400px;
}
</style>
