<template>
  <section>
    <!--<h1> SPLASH SCREEN </h1>
    <h2> need to check if loggedin and move to login screen </h2>-->
    <img src="http://10steps.sg/wp-content/uploads/article141/funnycouple_24.jpg">
  </section>
</template>


<script>
export default {
  name: 'splash',
  created(){
    var that = this;
        console.log('splash: CHECK is seession active - or logged in',this.$store.getters.fetchCurrUser)
        if(this.$store.getters.fetchCurrUser) {
        console.log('Splash: user already logged in (exists) - move to BROWSE!!!');
        setTimeout(function(){that.$router.push('Browse')}, 2000);      
      }
      else {
        console.log('Splash: user not logged in  - move to LOGGIN!!!');
        setTimeout(function(){that.$router.push('Login')}, 2000);      
     }
  },


  mounted() {
   // console.log('splash: waiting 3 seconds')
    // this.$router.push('Browse');
  },

//     watch:{
// this.$store.getters.curUser: function(cur){
//   if(!cur){
//   console.log('SPLASH: user logged in - move to BROWSE');
// this.$router.push('Browse');
//   } 
//   else{
//    console.log('SPLASH: user logged in - move to BROWSE');
//    this.$router.push('Login');
//   } 
// },
  computed: {
    //  users() {
    //       console.log('this.$store.usersMatched', this.$store.state.usersMatched);
    //       return this.$store.usersMatched;
    //     }
  },

}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.users-list {
  display: flex;
}

.users-list-item {
  background-color: lightgray;
  display: flex;
  flex-direction: row;
  width: 80%;
  margin-bottom: 2px;
  justify-content: space-between;
}

.user-photo {
  display: flex;
  flex-direction: column;
}

.last-chat-line {
  color: purple;
}

.buttons-zone {
  display: flex;
  flex-direction: column;
}
</style>
