<template>
  <div id="app">
    {{counter}}<br />
    <button v-on:click="counter=counter+1">Click+1</button>
    <!-- v-on:click = @click -->
    <button @click="clicked">Click+2</button>

    <hr />
    <!-- เส้น -->
    <h1>{{ message }}</h1>
    <br />
    <span v-text="message"></span>
    <br />
    <input type="text" v-model="message" />

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

    <hr />
    <!-- เส้น -->
    <select v-model="message">
      <option value="cake">Cake</option>
      <option value="candy">Candy</option>
      <option value="tea">Tea</option>
    </select>

    <hr />
    <!-- เส้น -->
    <textarea v-model="message"></textarea>

  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      counter:0,
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
  methods:{
    clicked: function(){
      this.counter=this.counter+2;
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
