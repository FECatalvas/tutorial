<template>
    <div id = "body">
    <b-container class="bv-example-row">
      <b-row id = "row">
        <b-col>

        </b-col>
        <b-col id="top" cols = "8" >

        <b-form @submit="onSubmit"> 
        <h4 class="text-lg font-weight-bold" style="color:#E3CD81FF">SIGN UP</h4>
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

          <b-button id="sign-up" type="submit" block variant="primary">Sign Up</b-button><br>
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
  background-image:url('https://cdn.pixabay.com/photo/2017/03/31/10/56/waffles-2190961_960_720.jpg');
  background-repeat:no-repeat;
  background-size:cover;
  padding:160px;
  height:913px;
}
#top {
  background-color: rgba(177, 179, 179,0.4) !important;
  padding: 3vw 4vw 5vw;
  border-radius: 4px;
  box-shadow: 2px 5px 16px 2px rgba(16, 16, 16, 0.18);
  text-align: center;
  margin-top: 125px;
}
.btn-block{
  margin-top:33px;
  background-color: #B1B3B3FF;
  border-color: #B1B3B3FF;
}

#sign-up{
  margin-bottom:0px;
}
</style>