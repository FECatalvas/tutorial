<template>
  <div id="card" >
    <center>
  <img height="100px" id="logo" src="/logo.png">
  <h1 id="brandname">Ms.SweetBakes</h1>
     <hr>
     <p>Ms.SweetBakes is an online baking class. It has all the baking courses where will you learn the necessary 
     skills you need to learn in order to bake your own cakes and pastries.</p>  
  </center>
  <b-img id="food1"src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRWyTQh7BTUSKjAFE883Ms3vEem7Yr-hFG46HB4bh0_ExH2pf4y" fluid alt="Responsive image"></b-img>
  <b-img id="food2"src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR4Utt9Zu_4Ki6SHe3FY7cqkahzkYeML2SydDErS-Pz3i5XV-fR" fluid alt="Responsive image"></b-img>
  <b-img id="food3"src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSJfNgLrtsuuU_Y_IDgGTbyhaUHZqhBN5aFY6O-_G3YSScTrKR6" fluid alt="Responsive image"></b-img>
  <b-img id="food4"src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTHPXu5sH7fcA-GmeyMN7SJIlbvqEg9so5zb0LF1rCYBoKUrBIGrg" fluid alt="Responsive image"></b-img>

</div>
</template>
<style lang='scss' scoped>
@import "~assets/colors.scss";
#card {
  margin-top: 10%;
}
#userIcon {
  width: $userIconWidth !important;
  height: $userIconHeight !important;
}
p{
      margin-top: 0;
    margin-left: 70px;
    margin-bottom: 1rem;
}
h4{
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
}
#food1,#food2,#food3,#food4{
border-radius:50px;
margin: 50px -10px 75px 95px;
}

#brandname{
  color: #E3CD81FF !important;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
</style>

<script>
export default {
  name: "card",
  data() {
    return {
      Uname: sessionStorage.getItem("Username")
    };
  },
  component: {

  },
  methods: {

  }
};
</script>