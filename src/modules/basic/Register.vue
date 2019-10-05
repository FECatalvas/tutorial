<template>
    <div id = "body">
    <b-container class="bv-example-row">
      <b-row id = "row">
        <b-col>

        </b-col>
        <b-col id="top" cols = "8" >

        <b-form @submit="onSubmit"> 
        <h4 class="text-lg font-weight-bold">SIGN UP</h4>
          <b-form-group id="input-group-0"  label-for="input-0" >
            <b-form-input id="input-0" v-model="form.username" type="text" required placeholder="Username"></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-1"  label-for="input-1">
            <b-form-input id="input-1" v-model="form.email" type="email" required placeholder="Email"></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-2" label-for="input-2">
            <b-form-input id="input-2" v-model="form.password" required placeholder="Password" type="password"></b-form-input>
          </b-form-group>
          
          <b-form-group id="input-group-3" label-for="input-3">
            <b-form-input id="input-3" v-model="form.confirmPassword" required placeholder="Confirm Password" type="password"></b-form-input>
          </b-form-group>

          <b-button id="login" type="submit" block variant="primary">Sign Up</b-button><br>
        </b-form>

        </b-col>
        <b-col>

        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import AUTH from 'services/auth'
// import ROUTER from 'router'
export default {
  data() {
    return {
      auth: AUTH,
      form: {
        username: "",
        email: "",
        password: "",
        confirmPassword: "",
      },
      show: true
    };
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault();
      sessionStorage.setItem("Password", this.form.password)
      sessionStorage.setItem("Username", this.form.username)
      sessionStorage.setItem("Email", this.form.email)
      AUTH.register(this.form.email, this.form.password)
      
      // ROUTER.push('/login')
    }
  }
};
</script>

<style scoped lang="scss">
@import "~assets/colors.scss";
#body{
  background-image:url('https://images.pexels.com/photos/612825/pexels-photo-612825.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500');
  background-repeat:no-repeat;
  background-size:cover;
  padding:110px;
}
#top{
  background-color: $bckg_color !important;
	padding: 3vw 4vw 5vw;
  border-radius: 4px;
  box-shadow: 2px 5px 16px 2px rgba(16, 16, 16, 0.18);
  text-align: center;

  }

.card-body{
  background-color:rgba(247, 247, 247,0.3)

}
/* #login {length: 20px; } */

.btn-block{
  margin-top:30px;
}
</style>