<template>
<form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search Jokes... ">
    <input type="submit" value="Search">
</form>
</template>

<script>
export default {
    name:'searchjokes',
    data(){
        return {
            text:''
        }
    },
    methods:{
        onSubmit(){
            this.$emit('search-text',this.text );
            this.text = '';
        }
    }
}
</script>

<style>

</style>
