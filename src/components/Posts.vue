<template>
    <!-- <h1>{{msg}}</h1> -->
    <div v-if="msg && msg.data">
        <div v-for="val in msg.data" :key="val.id">
        <div>{{val}}</div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'PostData',
    props: {msg: Object}
        
}
</script>
<style scoped>

</style>