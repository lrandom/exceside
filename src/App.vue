<template>
  <div class="app">
    <!--    <div v-for="(product,index) in products" :key="index">-->
    <!--      <div class="product">-->
    <!--        <div class="product-name">Tên sản phẩm : {{product.name}}</div>-->
    <!--        <div class="product-price">Giá sản phẩm : {{product.price}}</div>-->
    <!--        <img :src="product.image" alt="product">-->
    <!--      </div>-->
    <!--    </div>-->


    <!--    <div v-for="(product,index) in checkShowProduct" :key="index">-->
    <!--      <div class="product">-->
    <!--        <div class="product-name">Tên sản phẩm : {{ product.name }}</div>-->
    <!--        <div class="product-price">Giá sản phẩm : {{ product.price }}</div>-->
    <!--        <img :src="product.image" alt="product">-->
    <!--      </div>-->
    <!--    </div>-->
    <!--  </div>-->

        <div>
          <div class="title">Sản phẩm đắt nhất</div>
          <div class="product">
            <div class="product-name">Tên sản phẩm : {{maxPrice[0].name}}</div>
            <div class="product-price">Giá sản phẩm : {{maxPrice[0].price}}</div>
            <img :src="maxPrice[0].image" alt="product">
          </div>
        </div>
        <div>
          <div class="title">Sản phẩm rẻ nhất</div>
          <div class="product">
            <div class="product-name">Tên sản phẩm : {{minPrice[0].name}}</div>
            <div class="product-price">Giá sản phẩm : {{minPrice[0].price}}</div>
            <img :src="minPrice[0].image" alt="product">
          </div>
        </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cart: [],

      products: [
        {
          id: 1,

          name: "PS5",

          price: 5555,

          publicDate: "05-05-2021",

          image:
              "https://cdn.vjshop.vn/hightech/may-choi-game/ps5/sony-ps-5-1.jpg",

          hot: true,
        },

        {
          id: 2,

          name: "PS4",

          price: 4444,

          publicDate: "04-04-2021",

          image:
              "https://gmedia.playstation.com/is/image/SIEPDC/ps4-slim-image-block-01-en-24jul20?$native--t$",

          hot: true,
        },

        {
          id: 3,

          name: "PS3",

          price: 3333,

          publicDate: "03-03-2021",

          image:
              "https://game.haloshop.vn/image/catalog/blogs/ps3-co-con-dang-mua/ps3-co-con-dang-mua-21.jpg",

          hot: false,
        },
      ],

      paymentMethods: [
        {text: "COD", value: 1},

        {text: "Banking", value: 2},

        {text: "Ứng dụng bên thứ 3", value: 3},
      ],

      selectedPayment: 2,
    };
  },
  computed: {
    checkShowProduct() {
      return this.products.filter((product) => {
        if (product.hot) {
          return product;
        }
      });
    },
    maxPrice() {
      return this.products.filter((product) => {
        return Math.max(product.price);
      })
    },
    minPrice() {
      return this.products.filter((product) => {
        return Math.min(product.price);
      })
    },

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
