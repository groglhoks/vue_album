<template>

    <div class="parent">
        <div class="block">
            <div>
                <div class="sub_block_tab_left round_tab">
                    <div class="tab_name">
                        Каталог        
                    </div>
                    
                </div>
                <div class="sub_block_tab_right round_tab">
                    <div class="tab_name">
                        <div class="favorites_icon"></div>
                        <div class="right_tab_name">Избранное</div>        
                    </div>
                    
                </div>
            </div>
            <div class="sub_block_content">

                <!-- v-on:addPhoto="addPhoto" -->
                <User v-for="user in users"
                    v-bind:user="user" v-bind:key="user.id" @addPhoto="addPhoto"/> 
            </div>
        </div>
    </div>

</template>

<script>

    import User from './User.vue';

    export default {
        props: ['users'],
        components: {User},
        methods: {
            addPhoto(photo) {
                console.log(photo);
                // this.$emit('addPhoto', photo);
            } 
        }    
    }

</script>

<style>
</style>