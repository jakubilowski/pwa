<template>
  <div>
    <p>{{ name }}</p>
  </div>
</template>

<script>
import { type } from "os";

export default {
  name: "Person",
  props: {
    name: {
      type: String,
      default: () => "",
    },
    student: {
      type: Boolean,
      requier: true,
    },
  },
  created() {
    console.log(this.name, this.student);
  },
};
</script>

<style scoped></style>
