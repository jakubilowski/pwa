<template>
  <div>
    <h1>Strona domowa</h1>
    <bigImage
      image="https://hips.hearstapps.com/hmg-prod/images/champagne-beach-espiritu-santo-island-vanuatu-royalty-free-image-1655672510.jpg?crop=1.00xw:0.755xh;0,0.173xh&resize=1200:*"
    />
    <Person :name="personSzymon.name" :student="true" />
  </div>
</template>

<script>
import TopNav from "../components/nav/TopNav.vue";
import bigImage from "../components/gallery/bigImage.vue";
import Customer from "../components/models/customer";
import Person from "../components/person/person.vue";

export default {
  name: "IndexPage",
  data() {
    return {
      personSzymon: null,
    };
  },
  created() {
    this.personSzymon = this.person("Szymon", "1921111", "18");
  },
  components: { TopNav, bigImage, Person },
  methods: {
    person(name, salary, age) {
      return new Customer(name, salary, age);
    },
  },
};
</script>

<style scoped>
@import "@/assets/css/index.css";
</style>
