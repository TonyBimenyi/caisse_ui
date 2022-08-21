// eslint-disable-next-line vue/multi-word-component-names
<template>
  <div class="container">
    <div class="background">
        <div class="shape"></div>
        <div class="shape"></div>
    </div>
    <form v-on:submit.prevent="login_user">
        <h3>BIMBO Caisse App</h3>

        <label for="username">Username</label>
        <input type="text" v-model="form.email" placeholder="Enter your Username..." id="username">

        <label for="password">Password</label>
        <input type="password" v-model="form.password" placeholder="Password" id="password">
         <label for="password">Select Shop</label>
        <select name="" id="">
          <option value="">--Select--</option>
          <option value="">Bimbo SuperMarket</option>
          <option value="">Bimbo Pharma</option>
        </select>
        <button>Log In</button>
   
    </form>
    </div>
</template>

<script>
import axios from 'axios'
import Swal from 'sweetalert2'
export default {
 data(){
    return{
      form:{
        email:'',
        password:''
      }
    }
  },
   methods:{
     login_user(){
          axios
          .post(this.$store.state.url+'login',this.form)
          .then((resp) =>{
              console.log(resp["data"]["status"]);
              this.$store.state.user = resp.data 
              //this.loadlist();
              //reset form
             this.form.email = '';
             this.form.password = '';
             if(resp["data"]["status"] == "error")
             {
               Swal.fire({
                title: 'OPPS',
                text:   "error",
                icon: 'warning',
              
            });
             }
             else
             {
               Swal.fire({
                title: 'Hurry',
                text:   "You have been logged-in successfully",
                icon: 'success',
              
            });
            this.$router.push('/sales')
             }
              
          })
          .catch((e)=>{
              console.log(e);
               Swal.fire({
              title: 'Hurry',
              text:   e,
              icon: 'warning',
              
            });
          })
        }

  }
}
</script>

<style src='../assets/css/login.css' scoped>
  .container{
  background: black;
  }
</style>