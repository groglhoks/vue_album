<template>
    <div class="user_line_comp">
        <div @click="userClick" class="user_line line"> 
            <div class="user_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}" ></div>
            <div class="user_name"> {{user.name}} </div>
        </div>
    </div>

    <Album v-for="album in albums"
                    v-bind:album="album" v-bind:key="album.id" @addPhoto="addPhoto" @showModalPhoto="showModalPhoto"/>

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

        components: { Album },

        methods: {
            userClick: function (event) {
                this.expanded = !this.expanded;

                if (this.expanded) {
                    fetch('https://jsonplaceholder.typicode.com/albums?userId=' + this.user.id)
                        .then((response) => response.json())
                        .then((json) => {
                            this.albums = json;
                        });
                } else {
                    this.albums = [];
                }
            },
            addPhoto(photo) {
                this.$emit('addPhoto', photo);
            },
            showModalPhoto(photo) {
                this.$emit('showModalPhoto', photo)
            }
        }
    }

</script>