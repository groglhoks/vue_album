<template>
    <div class="parent">
        <div class="block">
            <div>
                <div class="sub_block_tab_left round_tab" v-bind:class="{ 'background_tab': isFavoritesPage() }"
                    @click="onCatalogTabClick">
                    <div class="tab_name">
                        Каталог
                    </div>
    
                </div>
                <div class="sub_block_tab_right round_tab" v-bind:class="{ 'background_tab': isCatalogPage() }"
                    @click="onFavoritesTabClick">
                    <div class="tab_name">
                        <div class="favorites_icon"></div>
                        <div class="right_tab_name">Избранное</div>
                    </div>
    
                </div>
            </div>
            <div v-if="isCatalogPage()" class="sub_block_content">
    
                <!-- v-on:addPhoto="addPhoto" -->
                <User v-for="user in users" v-bind:user="user" v-bind:key="user.id" @addPhoto="addPhoto" />
            </div>
    
            <div v-if="isFavoritesPage()" class="sub_block_content">
                <div class="photos_container">
                    <div class="photo_line">
                        <div class="photo_favorite_wrapper"><img src="/src/assets/photo_not_favorite.ico"></div>
                        <div class="photo_wrapper"><img src="https://via.placeholder.com/150/cda4c0"></div>
                    </div>
                    <div class="photo_line">
                        <div class="photo_favorite_wrapper"><img src="/src/assets/photo_not_favorite.ico"></div>
                        <div class="photo_wrapper"><img src="https://via.placeholder.com/150/74e371"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import User from './User.vue';

    export default {
        props: ['users'],
        components: {User},
        data() {
            return {
                page : "catalog"
            }
        },
        methods: {
            addPhoto(photo) {
                console.log(photo);
                // this.$emit('addPhoto', photo);
            },
            isCatalogPage() {
                return this.page === "catalog";
            },
            isFavoritesPage() {
                return this.page === "favorites";    
            },
            onFavoritesTabClick() {
                this.page = "favorites"        
            },
            onCatalogTabClick() {
                this.page = "catalog"
            }
        }    
    }

</script>

<style>
</style>