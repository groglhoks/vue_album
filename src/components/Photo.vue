<template>
    <div class="photo_line">
        <div class="photo_favorite_wrapper" @click="photoFavoriteWrapperClick">
            <img v-if="isFavorite" src="../assets/photo_favorite.ico" />
            <img v-else src="../assets/photo_not_favorite.ico"/>
        </div>
        <div class="photo_wrapper" @click="showModalPhoto">
            <img v-bind:src="photo.thumbnailUrl" v-bind:title="photo.title" />
        </div>
    </div>    
</template>

<script>

    import PhotoModal from './PhotoModal.vue'

    export default {
        props: ['photo'],
        data() {
            return {
                isFavorite: false,
                isModalOpen: false
            }
        },
        methods: {
            photoFavoriteWrapperClick() {
                this.isFavorite = !this.isFavorite;

                if (this.isFavorite) {
                    this.$emit('addPhoto', this.photo);
                }
            },
            showModalPhoto() {
                this.$emit('showModalPhoto', this.photo)
            }

        },
        components: {PhotoModal}
    }

</script>