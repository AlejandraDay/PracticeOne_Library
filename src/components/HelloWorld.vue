<template>
  <div>
    <h1>Library</h1>
    <br />
    <input v-model="nameInput" placeholder="escriba su nombre" />
    <br />
    <!--div :key="item.name" v-for="item in list">
      <br />
      <span> {{ item.name }}</span>
      <br />
      <span>{{ item.desc }}</span>
      <br />
    </div-->
    <br />
    <div>
      <table border="3" align="center">
        <thead>
          <th>Code</th>
          <th>Nombre</th>
          <th>Description</th>
          <th>Category</th>
        </thead>
        <tr :key="data.name" v-for="data in filteredList">
          <td>{{ data.code }}</td>
          <td>{{ data.name }}</td>
          <td>{{ data.desc }}</td>
          <td>{{ data.category }}</td>
        </tr>
      </table>
    </div>
    <br />
  </div>
</template>

<script>
//import item from "@/database/item.json";
//import Vue from "vue";
export default {
  name: "HelloWorld",
  components: {},
  data() {
    return {
      nameInput: "",
      selectedOption: "",
      radioSelect: "",
      radioOptionA: "",
      // item,
      list: [
        {
          code: 1,
          name: "name1",
          desc: "desc1",
          category: "Book"
        },
        {
          code: 2,
          name: "name2",
          desc: "desc2",
          category: "NewPaper"
        },
        {
          code: 3,
          name: "name3",
          desc: "desc3",
          category: "NewPaper"
        }
      ]
    };
  },
  computed: {
    filteredList() {
      return this.nameInput === ""
        ? this.list
        : this.list.filter(item => item.name === this.nameInput);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
