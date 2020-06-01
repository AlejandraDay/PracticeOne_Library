<template>
  <div>
    <!-- span>Name or Description</span>
    <br />
    <br />
    <input v-model="nameInput" placeholder="Search" /-->
    <br />
    <br />
    <table>
      <thead>
        <tr>
          <th :key="columnkey" v-for="columnkey in columns" class="tables">
            {{ columnkey }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr :key="item.data" v-for="item in filteredList">
          <td :key="key" v-for="key in columns">
            {{ item[key] }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    // data: Array,
    columns: Array,
    filterKey: String,
    filterCategory: String
    // msg: String
  },
  data() {
    return {
      selecteCategory: "",
      radioSelect: "",
      radioOptionA: "",
      list: [
        {
          code: 1,
          name: "The 100",
          description: "Science fiction novel",
          category: "Books"
        },
        {
          code: 2,
          name: "Los tiempos",
          description: "Bolivian newspaper",
          category: "Books"
        },
        {
          code: 3,
          name: "Tú",
          description: "It's about teen themes",
          category: "Magazines"
        },
        {
          code: 4,
          name: "Time",
          description: "It's about controversy",
          category: "Magazines"
        },
        {
          code: 5,
          name: "Food Network Magazine",
          description: "It's about good food and gastronomy",
          category: "Magazines"
        },
        {
          code: 6,
          name: "Little Prices",
          description: "children's book",
          category: "Books"
        },
        {
          code: 7,
          name: "One Hundred Years of Solitude",
          description: "Contemporary novel",
          category: "Books"
        },
        {
          code: 8,
          name: "The Hunger Games",
          description: "Science fiction novel",
          category: "Books"
        },
        {
          code: 9,
          name: "The Lord of the rings",
          description: "Science fiction novel",
          category: "Books"
        }
      ]
    };
  },
  computed: {
    filteredList() {
      var filterKey = this.filterKey && this.filterKey.toLowerCase();
      var filterCategory =
        this.filterCategory && this.filterCategory.toLowerCase();
      var data = this.list;
      if (filterCategory === "All") {
        filterKey = "";
      } else if (filterKey && filterCategory != "All") {
        data = data.filter(function(row) {
          return Object.keys(row).some(function(key) {
            return (
              String(row[key])
                .toLowerCase()
                .indexOf(filterKey && filterCategory) > -1
            );
          });
        });
      }
      return data;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../views/home.css" scoped></style>
