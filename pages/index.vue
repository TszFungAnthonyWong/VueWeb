<template>
  <div class="App">
    <h1>Home Page</h1>

    <div>
      First Name:
      <input v-model="firstName" placeholder="First Name"/>
    </div>

    <div>
      Last Name:
      <input v-model="lastName" placeholder="First Name"/>
    </div>

    <div>
      ID:
      <input v-model="id" placeholder="First Name"/>
    </div>
    
    <button v-on:click="click" >GO</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
    message: '',
      firstName: '',
      lastName: '',
      id: '',
      click: () =>{
           window.location = '/user/'+this.firstName+"-"+this.lastName+"-"+this.id;
      }
    };
  }
};
</script>

<style>
.App {
     text-align: center;
}
</style>
    