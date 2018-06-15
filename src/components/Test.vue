<template>
  <div class="test">
    <input type="text" v-model="title" /><br/>
    <h1>
      {{title}}
    </h1>
    <!-- <span v-html="title"></span> -->
    <!-- <p>{{user.firstname }}</p> -->
    <!-- <p>{{user.lastname }}</p> -->
    <span v-if="showname">{{user.firstname }}</span>
    <span v-else>Nobody</span>
    <ul>
      <li v-for="item in items">
          {{item.title}}
      </li>
    </ul>
    <button v-on:click="greet('Hello World')">Say Greetings..!!!</button>
    <br/>
    <br/>
    <input type="text" v-on:keyup="PressKey" v-on:keyup.enter="EnterHit"/>

    <hr />
    <label>First Name :</label><input type="text" v-model="user.firstname"/><br /><br />
    <label>Last Name :</label><input type="text" v-model="user.lastname"/><br />
    <h3>
      {{fullname}}
    </h3>
    <h2>
      {{msg}}
    </h2>
    <!-- <input type="text" v-on:keyup="PressKey" v-on:keyup.shift="EnterShift"/> -->
    <!-- <input type="text" v-on:keyup="PressKey" v-on:keyup.enter="EnterHit"/> -->
    <!-- <input type="text" v-on:keyup="PressKey" v-on:keyup.enter="EnterHit"/> -->
  </div>
</template>


<script>
export default{
  name : "test",
  props : {
    msg : {
      default : 'Foobar',
      type: String
    }
  },
  data(){
    return{
      title:"Hello Test World",
      user : {
        firstname: 'Rachit',
        lastname: 'Kapadia'
      },
      showname : true,
      items : [
        {title:"Jay Savsani(BC)"},
        {title:"Naresh Chaudhary"},
        {title:"Jay Modi(MC)"}
      ]
    }
  },
  methods : {
    greet: function(greeting) {
      alert(greeting);
    },
    PressKey: function(e) {
      console.log(e.target.value)
    },
    EnterHit :function(){
      console.log("You hit Enter")
    }
    // EnterShift: function(){
    //   console.log("Hit Shift")
    // }

  },
  computed : {
    fullname : function(){
      return this.user.firstname + " " + this.user.lastname;
    }
  }
}
</script>



<style scoped>

</style>
