<template>
  <div id="app">
    <h1>{{ message }}</h1>
    <br />
    <span v-text="message"></span>

    <hr />
    <!-- เส้น -->
    <h1 v-show="isShow">Hello!!</h1>

    <hr />
    <!-- เส้น -->
    <div v-bind:key="emp.id" v-for="emp in employees">
      <span v-bind:class="(emp.Salary>20000) ? 'high' : (emp.Salary>13000) ? 'medium' : 'low'">
      {{emp.name}}
      </span>

      <span v-if="emp.Salary>20000">***</span>
      <span v-else-if="emp.Salary>13000">**</span>
      <span v-else>*</span>
    </div>

    <hr />
    <!-- เส้น -->
    <a v-bind:href="urlSKRU">SKRU</a>

    <hr />
    <!-- เส้น -->
    <img v-bind:src="require('@/assets/' + pic + '.png')" width="150px" />


  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      pic:"logo",
      urlSKRU:"http://www.skru.ac.th",
      message: "Hello!!",
      isShow: true,
      employees: [
        { "id": 1, "name": "Jinny", "Salary": 15000 },
        { "id": 2, "name": "Rianny", "Salary": 13000 },
        { "id": 3, "name": "Plammy", "Salary": 22000 }
      ],
    }
  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.high{
  color: green;
}
.medium{
  color: rgb(255, 251, 0);
}
.low{
  color: red;
}
</style>
