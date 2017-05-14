<template>
  <div class="cards">
    <div class="card" v-for="(list, index) in lists">
      <p><em>Name:</em>&nbsp;{{ list.name }}</p>
      <p><em>Description:</em>&nbsp;{{ list.description }}</p>
      <p><em>Category:</em>&nbsp;{{ list.category }}</p>
      <p><em>Presentation Link:</em>&nbsp;{{ list.url }}</p>
      <p><em>SNS Link:</em>&nbsp;{{ list.sns }}</p>

      <ul>
        <!--li><button>Edit</button></li-->
        <li><button @click="deleteList(index)">Delete</button></li>
      </ul> 
    </div>
  </div>
</template>

<script>
export default {
  props: {
    lists: Array
  },
  methods: {
    deleteList (index) {
      if (this.lists[index]) {
        this.lists.splice(index, 1)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .cards {
    display: flex;
    flex-wrap: wrap;
    padding: 0 5em;
    margin: 10px 0;
  }

  .card {
    width: 30%;
    border: 1px solid #ddd;
    margin: 10px;
    padding: 10px;
  }

  ul {
    list-style: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin-bottom: 10px;
  }

  .button--delete {
    display: inline-block;
    border: 1px solid #ddd;
    padding: 4px 10px;
    margin-left: 10px;
    color: #ff0000;
  }
</style>
