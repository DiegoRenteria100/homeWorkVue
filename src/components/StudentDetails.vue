<template>
  <div class="card">
    <img :src="studentInfo.picture.large">
    <p class="info">{{`Name: ${studentInfo.name.first} ${studentInfo.name.last}` }}</p>
    <div v-if="showDetails" class="details">
      <p class="info">{{`Email: ${ studentInfo.email }`}}</p>
      <p class="info">{{`Phone Number: ${ studentInfo.phone }`}}</p>
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
  
<style scoped>
*{
  border-radius: 10px;
}
button{
  background-color: rgb(104, 107, 230);
  color: white;
  margin: 5px;
  padding: 5px;
  width: 100px;
}

.info{
width: 100%;
}

.card{
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  width: 300px;
  padding: 10px;
  margin: 5px;
  align-items: center;
  background-color: rgb(245, 252, 255);
}

.card:hover{
  background-color: rgb(253, 236, 203);
  box-shadow: 0 0 0 5px rgba(40, 54, 68, 0.07);
  shape-outside: border-box;
}

.details{
  padding: 5px;
  background-color: rgb(223, 224, 224);
  box-shadow: 0 0 0 5px rgba(40, 54, 68, 0.07);
}
</style>
  