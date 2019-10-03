<template>
  <div id="body">
    <b-container class="bv-example-row">
      <b-row id="row">
        <b-col></b-col>
        <b-col id="top" cols="8">
          <b-form @submit="onSubmit">
             <b-form-group id="emailAdd" description="We'll never share your email with anyone else.">
            <b-form-input
              id="userName"
              v-model="form.email"
              type="email"
              required
              placeholder="Enter email"
            ></b-form-input>
          </b-form-group>

            <b-form-group id="input-group-2" label-for="input-2">
              <b-form-input id="input-2" v-model="form.password" required placeholder="Password" type="password"></b-form-input>
            </b-form-group>

            <b-button id="login"  type="submit" block variant="primary">Log in</b-button>
          </b-form>
        </b-col>
        <b-col></b-col>
      </b-row>
    </b-container>
  </div>
</template>
<style scoped>

</style>

<script>
import AUTH from 'services/auth'
import $ from 'jquery'
// import ROUTER from 'router'
export default {
  data() {
    return {
      auth: AUTH,
      form: {
        email: "",
        password: ""
      },
      show: true
    };
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault();
      AUTH.login(this.form.email, this.form.password)
      // AUTH.setUser(this.form.email)
    },
    login(){
      let link= 'http://localhost:3000/user'
      $.ajax({
        url: link,
        method: 'POST',
        headers: {
          'Access-Control-Allow-Origin':'*'
        }
      }).then(response =>{
        alert(response.username)
      })
    }
  }
};
</script>

<style scoped lang="scss">
@import "~assets/colors.scss";
#top {
  background-color: $bckg_color !important;
  padding: 3vw 4vw 5vw;
  border-radius: 4px;
  box-shadow: 2px 5px 16px 2px rgba(16, 16, 16, 0.18);
  text-align: center;
  margin-top: 190px;
}

.input-group{
  margin-bottom:40px;
}
/* #login {length: 20px; } */
</style>