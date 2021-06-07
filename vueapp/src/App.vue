<template>
<div id='app'> Hello @{{user.username}} -{{fullName}} 
<strong>followers: </strong>{{followers}}
<button @click="followUser"> Follow ;</button>
</div>
</template>

<script>

export default {
  name: 'App',
  data()
  {
    return {
      followers:0,
      user:
      {
        id:1,
        username : 'Guruc-134',
        firstName : 'Guru',
        lastName:   'Charan',
        email : 'guruc134@gmail.com',
        isAdmin : true
      }
    }
  },
  watch: {
    followers( newFollowerCount, oldFollowerCount)
    {
      if(oldFollowerCount < newFollowerCount){
        console.log(`${this.user.username} has gained follower`)
      }
    }
  },
  computed :{
    fullName(){
      return `${this.user.firstName} ${this.user.lastName}`;
    }
  },
  methods:
  {
    followUser(){
      this.followers++;
    }
  },
  mounted() 
  {
    this.followUser()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align:center;
 
}
</style>
