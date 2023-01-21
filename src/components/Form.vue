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
                <User v-for="user in users" v-bind:user="user" v-bind:key="user.id" @addPhoto="addPhoto" @showModalPhoto="showModalPhoto"/>
            </div>
    
            <div v-if="isFavoritesPage()" class="sub_block_content">
                <Favorites v-bind:favorites="favorites"/>    
            </div>
        </div>
    </div>

    <PhotoModal v-if="showModal" @close_modal="close_modal" v-bind:modalPhotoUrl="modalPhotoUrl"/>
</template>

<script>

    import User from './User.vue';
    import Favorites from './Favorites.vue';
    import PhotoModal from './PhotoModal.vue';

    export default {
        props: ['users'],
        components: {User, Favorites, PhotoModal},
        data() {
            return {
                page : "catalog",
                favorites: [],
                modalPhotoUrl: "",
                showModal: false,
            }
        },
        methods: {
            addPhoto(photo) {
                this.favorites.push(photo);
                localStorage.setItem('favorites', JSON.stringify(this.favorites));
            },
            showModalPhoto(photo) {
                console.log(photo); 
                this.modalPhotoUrl = photo.url;
                this.showModal = true;       
            },
            close_modal() {
                this.showModal = false;    
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
        },
        mounted() {

            const data_favorites = localStorage.getItem("favorites");
            if (data_favorites) {
                this.favorites = JSON.parse(data_favorites);   
            }
        } 
    }

</script>