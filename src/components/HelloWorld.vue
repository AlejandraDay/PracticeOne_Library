<template>
  <div>
    <h1>Library</h1>
    <input v-model="nameInput" placeholder="escriba su nombre" />
    <br />
    <br />
    <div>
      <table border="3" align="center">
        <thead>
          <th>Code</th>
          <th>Name</th>
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
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      nameInput: "",
      selectedOption: "",
      radioSelect: "",
      radioOptionA: "",
      list: [
        {
          code: 1,
          name: "item1",
          desc: "desc1",
          category: "Books"
        },
        {
          code: 2,
          name: "item2",
          desc: "desc2",
          category: "Books"
        },
        {
          code: 3,
          name: "intem3",
          desc: "desc3",
          category: "Books"
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
