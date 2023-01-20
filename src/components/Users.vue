<script>

    import User from './User.vue';

    export default {
        props: ['users'],
        components: {User}    
    }

</script>

<template>

    <div class="parent">
        <div class="block">
            <div>
                <div class="sub_block_tab_left round_tab">
                    Каталог
                </div>
                <div class="sub_block_tab_right round_tab">
                    <div class="favorites_icon"></div>
                    <div class="right_tab_name">Избранное</div>
                </div>
            </div>
            <div class="sub_block_content">

                <User v-for="user in users"
                    v-bind:user="user" v-bind:key="user.id" /> 
            </div>
        </div>
    </div>

</template>