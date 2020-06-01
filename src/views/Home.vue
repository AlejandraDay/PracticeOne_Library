<template>
  <div class="home" id="Home">
    <br />
    <br />
    <br />
    <img alt="Vue logo" src="../assets/logo.jpg" />
    <br />
    <!--img alt="Vue logo" src="../assets/logo.png" /-->
    <br />
    <br />
    <label>Search by Name or Description: </label>
    <input v-model="searchCodeOrName" />
    <label> Select a Category: </label>
    <select v-model="selecteCategory">
      <option>Books</option>
      <option>Magazines</option>
      <option>Newspapers</option>
      <option>Others</option>
      <option>All</option>
    </select>
    <HelloWorld
      :columns="columns"
      :filterKey="searchCodeOrName"
      :filterCategory="selecteCategory"
    >
    </HelloWorld>
    <br />
    <br />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  data() {
    return {
      //msg: "Welcome to Your Library",
      searchCodeOrName: "", //name or description
      selecteCategory: "All", //category
      columns: ["code", "name", "description", "category"]
    };
  }
};
</script>
<style src="./home.css" scoped></style>
