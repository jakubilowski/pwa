<template>
  <div class="nav">
    <div class="mojItem">
      <ul>
        <li><NuxtLink to="/">Strona domowa</NuxtLink></li>
        <li><NuxtLink to="/onas">O nas</NuxtLink></li>
        <li><NuxtLink to="/nowa">Nowa</NuxtLink></li>
        <li><NuxtLink :to="'/cars/'">Cars</NuxtLink></li>
        <li><NuxtLink :to="'/nasa'">Nasa</NuxtLink></li>
      </ul>
    </div>
  </div>
</template>

<script></script>

<style scoped>
/* .topElement {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: royalblue;
  color: white;
  border-bottom: 2px solid black;
} */

.nav {
  display: flex;
  height: 100%;
  width: 100%;
  max-height: 80px;
  background-color: black;
  border-bottom: 4px solid gray;
  flex-direction: row;
}
.mojItem {
  font-size: 20px;
  color: white;
  margin-right: 10px;
  text-decoration: none;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: black;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: grey;
}
</style>
