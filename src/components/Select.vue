<template>
    <select v-model="selected" @click.prevent="$emit ('search', selected)">
        <option disabled value="">Generi</option>
        <option value="Rock" >Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
    
    <!-- <span>Selected: {{ selected }}</span> -->
</template>

<script>
export default {
    name : "Select",
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