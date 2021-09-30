<template>
    <select v-model="selected" @click.prevent="$emit ('search', selected)">
        <option value="">Tutti gli artisti</option>
        <option value="Bon Jovi" >Bon Jovi</option>
        <option value="Queen">Queen</option>
        <option value="Sting">Sting</option>
        <option value="Steve Gadd Band">Steve Gadd Band</option>
        <option value="Iron Maiden">Iron Maiden</option>
        <option value="Eric Clapton">Eric Clapton</option>
        <option value="Deep Purple">Deep Purple</option>
        <option value="Metallica">Metallica</option>
        <option value="Dave Weckl">Dave Weckl</option>
        <option value="Michael Jacjson">Michael Jackson</option>
    </select>
</template>

<script>
export default {
    name : "SelectGenre",
    data : function(){
        return {
            selected:"",
        }
    },
    methods : {
       
    },
 
}
</script>

<style lang="scss" scoped>

</style>