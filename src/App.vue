<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <section class="container">
      <div id="form">
        <Form @newRecord="addRecord" />
      </div>
      <div id="table">
        <Table :allData="tableData" />
      </div>
    </section>
  </div>
</template>

<script>
import Form from './components/Form'
import Table from './components/Table'

export default {
  name: 'app',
  components: {
    Form, Table
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      tableData: []
    }
  },
  methods: {
    addRecord(data) {
      this.tableData.push({
        email: data.email,
        name: data.name, 
        food: data.food
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
    width: 90%;
    height: 500px;
    background: rgb(242, 243, 205);
    margin: auto;
    padding: 10px;
}
#form {
  width: 45%;
  height: 400px;
  float: left;
}
#table{
  margin-left: 45%;
  padding-left: 10px;
  height: 400px;
}
</style>
