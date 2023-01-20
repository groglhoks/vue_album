<template>
    <div class="album_line_comp">
        <div class="album_line" @click="albumClick">
            <div class="album_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}"></div>
            <div class="album_name"> {{ album.title }}  </div>
        </div>
    </div> 
    <Photos v-bind:photos="photos"/>
</template>

<script>

import Photos from './Photos.vue';

export default {
    props: ['album'],

    data() {
        return {
            expanded: false,
            photos: []
        }
    },

    // mounted() {
    //         console.log(album)
    //     }
    
    methods: {
        albumClick() {
            this.expanded = !this.expanded;

            if (this.expanded) {
                fetch('https://jsonplaceholder.typicode.com/photos?albumId=' + this.album.id)
                    .then((response) => response.json())
                    .then((json) => {
                        this.photos = json;

                        console.log(this.photos);
                    });
            } else {
                this.photos = [];
            }
        }
       
    },

    components: {Photos}
// }
}
</script>

<style>
.album_line {
            float: left;
            height: 40px;
            width: 100%;
            background-color: blueviolet;
            border: 1px solid #aaa;
        }
</style>
