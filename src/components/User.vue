<template>
    <div class="user_line_comp">
        <div @click="userClick" class="user_line"> 
            <div class="user_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}" ></div>
            <div class="user_name"> {{user.name}} </div>
        </div>
    </div>

</template>

<script>

export default {
    props: ['user'],

    data() {
        return {
            expanded: false
        }    
    },

    methods: {
        userClick: function (event) {
            // `this` inside methods points to the Vue instance
            // alert('user click ' + this.user.id + '!')
            // `event` is the native DOM event
            // if (event) {
            //     alert(event.target.tagName)
            // }

            this.expanded = !this.expanded;
            console.log(this.expanded);
        }
    }
}

</script>