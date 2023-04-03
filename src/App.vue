<template>
  <div class="container">
    <header>
      <h1>Lista de estudiantes cursando el último año</h1>
    </header>
    <div class="cartas">
      <student-details v-for="(student,idx) in students" :key="idx" :student-info="student"></student-details>
    </div>
    <footer></footer>
  </div>
</template>

<script>
import StudentDetails from './components/StudentDetails.vue';
import axios from "axios";

export default {
  name: 'App',
  components: {
    StudentDetails
  },
  data() {
    return {
      students: null,
    }
  },
  mounted() {
    axios
      .get("https://randomuser.me/api/?results=30&inc=name,email,phone,picture&noinfo")
      .then((response) => (this.students = response.data.results));
      console.log(this.students);
  },
  methods: {
    // letterCounter(name){
    //   return name.lenght;
    // }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #0b0d0f;
  margin: 0px;
}
.cartas{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: center;
}
header h1{ 
  background-color: rgb(192, 231, 251);
  margin: 0;
}
.container{
  background-color: #0b0d0f;
  margin: 0;
  height: 100%;
  width: 100%;
}

body{
  background-color: #0b0d0f;
  margin: 0;
}

</style>
