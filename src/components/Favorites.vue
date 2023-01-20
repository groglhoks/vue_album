<template>
    <div v-if="favorites.length > 0" class="photos_container_favorites">
        <div class="photo_line" v-for="favorite of favorites"  v-bind:key="favorite.id">
            <div class="photo_favorite_wrapper">
                <img src="/src/assets/photo_favorite.ico">
            </div>
            <div class="photo_wrapper">
                <img v-bind:src="favorite.thumbnailUrl" />
            </div>
            <div class="favorites_photo_name">{{ favorite.title }}</div>
        </div>
    </div>
    <div v-if="favorites.length == 0" class="favorites_empty">
        <div class="favorites_empty_img"><img src="../assets/favorites_empty.png"/></div>
        <div class="favorites_empty_text"><strong>Список избранного пуст</strong><br>
        добавляйте изображения, нажимая на звездочки
    </div>
        
    </div>
</template>

<script>

export default {
        props: ['favorites']
}


</script>