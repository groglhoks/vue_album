<template>

    <div class="photos_line_comp" v-if="photos.length > 0">
        <div class="photos_container_wrapper line">
            <div class="photos_container">
                <Photo v-for="photo in photos" v-bind:key="photo.id" v-bind:photo="photo" @addPhoto="addPhoto" @showModalPhoto="showModalPhoto"/>
            </div>
        </div>
    </div>
</template>

<script>

    import Photo from './Photo.vue'

    export default {
        props: ['photos'],
        components: {Photo},
        methods: {
            addPhoto(photo) {
                this.$emit('addPhoto', photo);
            },
            showModalPhoto(photo) {
                this.$emit('showModalPhoto', photo)
            }
        }
    }

</script>