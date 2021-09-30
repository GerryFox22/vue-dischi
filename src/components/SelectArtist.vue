<template>
  <select v-model="selected" @click.prevent="$emit ('search', selected)">
        <option value="">Tutti i generi</option>
        <option value="Rock" >Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</template>

<script>
export default {
    name : "SelectArtist",
    data : function(){
        return {
            selected:"",
        }
    },
}
</script>

<style>

</style>