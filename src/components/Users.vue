<template>
  <div class="users">
    <h1>
      Users
    </h1>
    <form v-on:submit="addUser">
      <label>Name : </label><input type="text" v-model="newUser.name" placeholder="Enter name"/>
      <br />
      <br />

      <label>Enter Email : </label><input type="text" v-model="newUser.email" placeholder="Enter Email"/>
      <br />
      <br />

      <input type="submit" value="submit" />

    </form>

    <ul>
      <li v-for="user in users ">
        <input type="checkbox" v-model="user.contacted"/>
        <span :class="{contacted: user.contacted}">
          {{ user.name }}: {{user.email}} <button v-on:click="deleteUser(user)">Del</button>
        </span>

      </li>
    </ul>

  </div>
</template>


<script>
export default{
  name : "users",
  data(){
    return{
      newUser : {},
      users : [
        {
          name : "Rachit Kapadia",
          email : "rachit@quixom.com",
          contacted : false
        },
        {
          name : "Jay Savsani",
          email : "rachit@quixom.com",
          contacted : false
        },
        {
          name : "Naresh Chaudhary",
          email : "rachit@quixom.com",
          contacted : false
      }
      ]

    }
  },
  methods : {
    addUser: function(e){
      this.users.push(
        {
          name : this.newUser.name,
          email : this.newUser.email,
          contacted : false
        }
      );

      e.preventDefault();
    },
    deleteUser: function(){
      this.users.splice(this.users.indexOf(user,1));
    }
  }
  }
</script>



<style scoped>
.contacted{
  text-decoration:line-through;
}
</style>
