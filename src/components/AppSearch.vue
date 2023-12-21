<template lang="">
    <div>
        <input type="text" v-model="searchedString">
        <button @click="$emit(`search`searchedString)">Search </button>
    </div>


</template>
<script>
export default {
    name: `AppSearch`,

    data() {
        return {
            searchedString: ``,
        }
    }
}
</script>
<style lang=""> 
</style>