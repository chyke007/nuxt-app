<template>
<nuxt-link :to="'jokes/'+id">
 <div class="">
        <p>{{joke}}</p>
        <hr/>
 </div>
</nuxt-link>
  
</template>

<script>
export default {
    name:'joke',
    props:['joke','id']
}
</script>

<style>
.joke{
    padding:1rem;
    border:1px dotted #ccc;
    margin: 1rem 0;
}
</style>
