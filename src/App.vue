<script>
import HelloWorld from './components/HelloWorld.vue'
import Users from './components/Users.vue'

export default {
  name: "app",
  components: {Users},
  data() {
    return {
      users: []
    }
  },
  mounted() {
    // console.log("mounted");
    fetch('https://jsonplaceholder.typicode.com/users')
      .then((response) => response.json())
      .then((json) => {
        this.users = json;
        // console.log(this.users)
      });
  }
}
</script>

<template>
  <div>test</div> 
  <Users v-bind:users="users" />
</template>
 
