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
                <Favorites v-bind:favorites="favorites"/>    
            </div>
        </div>
    </div>
</template>

<script>

    import User from './User.vue';
    import Favorites from './Favorites.vue'

    export default {
        props: ['users'],
        components: {User, Favorites},
        data() {
            return {
                page : "catalog",
                favorites: []
            }
        },
        methods: {
            addPhoto(photo) {
                this.favorites.push(photo);
                console.log(this.favorites);
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