<script>
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
    fetch('https://jsonplaceholder.typicode.com/users')
      .then((response) => response.json())
      .then((json) => {
        this.users = json;
      });
  }
}
</script>

<template>
  <div>test</div> 
  <Form v-bind:users="users" />
</template>
 
