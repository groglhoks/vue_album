<template>
    <div class="photo_line">
        <div class="photo_favorite_wrapper" @click="photoFavoriteWrapperClick">
            <img v-if="isFavorite" src="../assets/photo_favorite.ico" />
            <img v-else src="../assets/photo_not_favorite.ico"/>
        </div>
        <div class="photo_wrapper">
            <img v-bind:src="photo.thumbnailUrl" />
        </div>
    </div>    
</template>

<script>

    export default {
        props: ['photo'],
        data() {
            return {
                isFavorite: false
            }
        },
        methods: {
            photoFavoriteWrapperClick() {
                this.isFavorite = !this.isFavorite;

                if (this.isFavorite) {
                    this.$emit('addPhoto', this.photo);
                }
            }

        }
    }

</script>