<template>
  <div class="card">
    <img :src="studentInfo.picture.large">
    <p>{{`Name: ${studentInfo.name.first} ${studentInfo.name.last}` }}</p>
    <div v-if="showDetails">
      <p>{{ studentInfo.email }}</p>
      <p>{{ studentInfo.phone }}</p>
      <!-- <p v-if="studentInfo.age >= 18">Last year in school</p> -->
    </div>
    <button @click="show()">{{showDetails ? 'Hide details' : 'Show details'}}</button>
  </div>
</template>
  
<script>

export default {
  name: 'StudentDetails',
  props: {
    studentInfo: { type: Object, default: () => { } },
  },
  data() {
    return {
      showDetails: false,
    }
  },
  methods: {
    show(){
      this.showDetails = !this.showDetails;
    }
  },
}
</script>
  
<style>
button{
  background-color: black;
  color: white;
  margin: 5px;
}

.card{
  border: 1px solid;
  width: 250px;
  padding: 10px;
  margin: 5px;
  justify-content: center;
  background-color: rgb(192, 231, 251);
}

</style>
  