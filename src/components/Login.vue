<template>
<div>
  <p v-if="error.length">
    <b> {{errorMain}} </b>
    <ul>
      <li v-for="e in error" v-bind:key="e.id">
        {{e}}
      </li>
    </ul>
  </p>
  <form @submit="login">
    <input type="text" name="name" placeholder="enter name" v-model="name"> <br> <br>
    <input type="password" name="password" placeholder="enter password" v-model="password"> <br> <br>
    <button type="submit">Login</button>
  </form>
</div>
</template>
<script>
export default {
  name: 'Login',
  data() {
    return{
      error:[],
      name:null,
      password:null,
      errorMain: "Please correct the following errors"
    }
  },
  methods: {
    login(e){

      this.error=[];

      if(this.name && this.password){
        console.log("no error");
        //return true;
      }
      if(!this.name){
      this.error.push("user name is required");     
      }
      if(!this.password){
        this.error.push("password is required");
      }

      console.warn("Hello", this.error);
      e.preventDefault(); //prevents from reloading

    }
  }
}
</script>
