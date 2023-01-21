<template>
    <div class="album_line_comp">
        <div class="album_line line" @click="albumClick">
            <div class="album_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}"></div>
            <div class="album_name"> {{ album.title }}  </div>
        </div>
    </div> 
    <Photos v-bind:photos="photos" @addPhoto="addPhoto" @showModalPhoto="showModalPhoto"/>
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
    
    methods: {
        albumClick() {
            this.expanded = !this.expanded;

            if (this.expanded) {
                fetch('https://jsonplaceholder.typicode.com/photos?albumId=' + this.album.id)
                    .then((response) => response.json())
                    .then((json) => {
                        this.photos = json;
                    });
            } else {
                this.photos = [];
            }
        },
        addPhoto(photo) {
            this.$emit('addPhoto', photo);
        },
        showModalPhoto(photo) {
            this.$emit('showModalPhoto', photo)
        }
       
    },

    components: {Photos}
}
</script>
