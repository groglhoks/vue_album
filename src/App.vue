<script>
import HelloWorld from './components/HelloWorld.vue'
import RawTemplate from './components/RawTemplate.vue'
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
    console.log("mounted");
    fetch('https://jsonplaceholder.typicode.com/users')
      .then((response) => response.json())
      .then((json) => {
        this.users = json;
        console.log(this.users)
      });
  }
}

// onMounted() {
//   this.$nextTick(function () {
//     // Код, который будет запущен только после
//     // отрисовки всех представлений
//   })
// }

// onMounted(() => {
//   console.log("mounted")

//   fetch('https://jsonplaceholder.typicode.com/users')
//   .then((response) => response.json())
//   .then((json) => 

//     // this.todos = json
//     console.log(json)
  
//   );


// })


</script>

<template>
  <div>test</div> 
  <!-- <RawTemplate /> -->
  <Users v-bind:users="users" />
</template>
 
