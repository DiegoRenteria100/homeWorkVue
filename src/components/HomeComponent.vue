<template>
  <div class="container">
    <header>
      <h1>List of students studying the last year</h1>
    </header>
    <div class="studentsList">
      <student-details v-for="(student,idx) in students" :key="idx" :student-info="student"></student-details>
    </div>
  </div>
</template>

<script>
import StudentDetails from './StudentDetails.vue';
import axios from "axios";

export default {
  name: 'HomeComponent',
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
  },
}
</script>
<style scoped>

.studentsList{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-evenly;
}
header h1{ 
  background-color: rgb(80, 82, 218);
  color: aliceblue;
  margin: 10px;
  text-align: center;
  box-sizing: content-box;
}
</style>
