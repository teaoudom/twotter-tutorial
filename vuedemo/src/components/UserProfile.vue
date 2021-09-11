<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome!! this is my first vue.app"/> -->
  <div class="user-profile">
     <div class="user-profile_user-panel">
         <h1 class="user-profile_username">
             @{{user.username}}
         </h1>
         <div class="user-profile_admin-badge" v-if="user.isAdmin">
             Admin
         </div>
         <div class="user-profile_follower-count">
             <strong>Followers: </strong>{{followers}}
         </div>
     </div>
  </div>
</template>

<script>
//import { computed } from '@vue/runtime-core' class="user-profile_twoots-wrapper" class="user-profile_twoot" 
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'UserProfile',
  data(){
    return{
        followers:0,
        user:{
          id:1,
          username:'Mr. Oudom1',
          firstName:'Tea',
          lastName:'Oudom',
          email:'teaoudom@gmail.com',
          isAdmin:true
        }
    }
  },
  watch:{ //when data change : Watch will execute
    followers(nFollowCount,oFollowCount){
      if(oFollowCount < nFollowCount){
         console.log(`${this.user.username} has gained a followers!`)
      }
    }
  },
  computed: {
    fullName(){
      return `${this.user.firstName} ${this.user.lastName}`;
    }
  },
  methods:{
    followUser(){
      this.followers+=1;
    }
  },
  mounted(){ //run when we first load to component
    this.followUser();
  }
  // components: {
  //   HelloWorld
  // }
}
</script>

<style>
    .user-profile {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 100%;
    padding: 50px 5%;
    }
    .user-profile_user-panel{
        display: flex;
        flex-direction: column;
        padding: 20px;
        padding:20px;
        background-color: white;
        border-radius: 5px;
        border: 1px solid #DFE3E8;
        margin-bottom: auto;
    }

    .user-profile_admin-badge{
        background: rebeccapurple;
        color:white;
        border-radius: 5px;
        margin-right: auto;
        padding: 0 10px;
        font-weight: bold;
    }

     .user-profile__twoots-wrapper {
    display: grid;
    grid-gap: 10px;
    margin-bottom: auto;
  }

    h1{
        margin: 0;
    }

</style>
