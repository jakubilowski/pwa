<template>
  <div>
    <h1>O nas</h1>
    <button @click="showInfo">kliknij mnie</button>
  </div>
</template>

<script>
import TopNav from "../components/nav/TopNav.vue";
import Student from "../components/models/student";

export default {
  name: "OnasPage",
  created() {
    this.student();
  },

  components: { TopNav },
  methods: {
    showInfo: () => {
      console.log("Witaj w konsoli");
      alert("Witaj");
    },
    student() {
      let firstStudent = new Student("Szymon", "Paltowski", "PA1.1", true);
      let secondStudent = {
        name: "Agata",
        surname: "Paltowska",
        group: "PA1.1",
        isGood: false,
      };
      console.log(firstStudent);
      console.log(secondStudent);
    },
  },
};
</script>

<style scoped></style>
