<template>
  <div class="container center">
    <h1>Nasa {{ currentCollection }}</h1>

    <input v-model="message" placeholder="search..." />
    <button @click="find()">Szukaj</button>
    <div
      style="
        display: flex;
        flex-wrap: wrap;
        width: 100%;
        justify-content: center;
      "
    >
      <template v-for="value in dataArr">
        <template v-for="(link, index) in value.links">
          <img
            alt=""
            v-if="index === 0"
            :data-index="index"
            :src="link.href"
            style="width: 100px; height: 100px; object-fit: cover; padding: 5px"
          />
        </template>
      </template>

      <!-- <img
        :src="value.links[0].href"
        v-for="value in dataArr"
        :key="value.href"
        style="width: 100px; height: 100px; object-fit: cover; padding: 5px"
      /> -->
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "index",

  created() {
    this.fetchData("sun");
  },

  data() {
    return {
      dataArr: [],
      message: "",
      currentCollection: "",
    };
  },

  methods: {
    find() {
      this.fetchData(this.message);
    },
    async fetchData(search) {
      await axios
        .get("https://images-api.nasa.gov/search?q=" + search)
        .then((res) => {
          this.dataArr = res.data.collection.items;
          this.currentCollection = search;
          this.message = "";
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped>
.center {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
