<script>
import HelloWorld from './components/HelloWorld.vue'
import Form from './components/Form.vue'

export default {
  name: "app",
  components: {Form},
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
  <Form v-bind:users="users" />
</template>
 
