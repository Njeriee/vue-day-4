<template>
<div class="container" v-if="showForm">
  <form class="">
    <div class="fill">
      <div>
        <label> First Name</label>
        <input type="text" v-model="first_name">
      </div>
      <div>
        <label> Last Name</label>
        <input type="text" v-model="last_name">
      </div>
    </div>
    <div class="fill">
      <div>
        <label> Email</label>
        <input type="email" v-model="email">
      </div>
      <div>
        <label>Phone No</label>
        <input type="text">
      </div>
    </div>
        <!-- v-model for check boxes -->
  <div class="terms-and-conditions">
    <input type="checkbox" v-model = "terms">
    <label>Accept term and condtions</label>
  </div>
  <!-- v-model for select optipns -->
  <div>
      <p>County</p>
  <select name="" id="" v-model= "county">
    <option value="kiambu">Kiambu</option>
    <option value="Nairobi">Nairobi</option>
    <option value="Kisumu">Kisumu</option>
    <option value="Nakuru">Nakuru</option>
  </select>
  </div>
  </form>
</div>
  <div>
    <button @click="toggleform"> 
      <span v-if = "showForm">hide form </span>
      <span v-else>show form</span>
    </button>
</div>

</template>

<script> 
export default{
  data(){
    return{
      // track first name, last name and email input
      first_name:"",
      last_name:'',
      email: "",
      terms:"",
      county:"",
      // objct for event handling. here the event is @click
      showForm: true

    }
  },
  methods: {
    toggleform(){
      this.showForm = !this.showForm
    }
  }
}
</script>

<style>
* {
  font-family: sans-serif;  
  font-size: large;
}
.container{
  position: absolute;
  top:25%;
  left:25%;
  /* right: 25%; */
  background: white;
  padding: 80px;
  border-radius:5%;
  
}
form{
  display:inline-grid;
  grid-template-columns: auto auto;
  /* text-align: center; */
}
label{
  margin-right: 5px;
}
input{
  margin: 10px;
  padding: 10px 6px;
  width: 100%;

}
.fill{
  padding: 20px;
}
.submit-button{
  width: 80px;
  margin-right: 5px;
}
.terms-and-conditions {
  display: inline-block;
  color: grey;
  font-size:medium;
}

</style>