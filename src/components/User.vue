<template>
    <div class="user_line_comp">
        <div @click="userClick" class="user_line"> 
            <div class="user_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}" ></div>
            <div class="user_name"> {{user.name}} </div>
        </div>
    </div>

    <Album v-for="album in albums"
                    v-bind:album="album" v-bind:key="album.id" />

</template>

<script>

import Album from './Album.vue';

export default {
    props: ['user'],

    data() {
        return {
            expanded: false,
            albums: []
        }    
    },

    components: {Album},

    methods: {
        userClick: function (event) {
            // `this` inside methods points to the Vue instance
            // alert('user click ' + this.user.id + '!')
            // `event` is the native DOM event
            // if (event) {
            //     alert(event.target.tagName)
            // }

            this.expanded = !this.expanded;
            // console.log(this.expanded);

            if (this.expanded) {
                fetch('https://jsonplaceholder.typicode.com/albums?userId=' + this.user.id)
                    .then((response) => response.json())
                    .then((json) => {
                        this.albums = json;
                    });
            } else {
                this.albums = [];
            }
        }
    }
}

</script>

<style>

.user_line {
    float: left;
    height: 40px;
    width: 100%;
    background-color: blueviolet;
    border: 1px solid #aaa;
}

</style>