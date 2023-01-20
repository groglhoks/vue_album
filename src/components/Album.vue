<template>
    <div class="album_line_comp">
        <div class="album_line" @click="albumClick">
            <div class="album_row_icon row_icon" v-bind:class="{'expand_icon' : !expanded, 'collaps_icon' : expanded}"></div>
            <div class="user_name"> {{ album.title }}  </div>
        </div>
    </div>    
</template>

<script>
export default {
    props: ['album'],

    data() {
        return {
            expanded: false
        }
    },

    // mounted() {
    //         console.log(album)
    //     }
    
    methods: {
        albumClick() {
            this.expanded = !this.expanded;
        }
       
    }
// }
}
</script>
