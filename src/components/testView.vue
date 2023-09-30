<template>
    <!-- v-model di gunakan untuk two-way data binding sama dengan keyup pada
      javasript -->
    <input type="text" v-model="name" />
    <h2>Hai, {{ name }}</h2>
    <button @click="changeName">Change Name</button>
    <!-- perulangan v-if dan v-else -->
    <div v-if="products.length">
      <!-- perulaangan v-for  menggunakan data-->
      <!-- <ul>
              <li v-for="product in products" :key="product.id">
                  {{ product.title }}
                  -
                  {{ product.price }}
              </li>
          </ul> -->
      <!-- perulaangan v-for  menggunakan data end -->
  
      <input type="text" v-model="cari" placeholder="Cari" />
      <!-- perulaangan v-for  menggunakan computed-->
      <ul>
        <li v-for="product in cariData" :key="product.id">
          {{ product.title }}
          -
          {{ product.price }}
        </li>
      </ul>
      <!-- perulaangan v-for  menggunakan data end -->
    </div>
    <div v-else>
      <p>Data Not Found</p>
    </div>
  </template>
  
  <script>
  export default {
    name: "testView",
    // components: { }
    data() {
      return { name: "Islahatun Nufusi", products: [], cari: "" };
    },
    methods: {
      // function
      changeName() {
        this.name = "Ida Hamdiyatun Nafiah";
      },
    },
  
    created() {
      this.products = [
        {
          id: 1,
          title: "product 1",
          price: 3000,
        },
        {
          id: 2,
          title: "product 2",
          price: 6000,
        },
        {
          id: 3,
          title: "product 3",
          price: 9000,
        },
      ];
    },
  
    computed: {
      cariData() {
        return this.products.filter((item) => {
          return item.title.match(this.cari);
        });
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