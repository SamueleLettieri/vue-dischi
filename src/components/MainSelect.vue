<template>
  <div class="text-center p-5"> 
    <select name="" id="" v-model="value" @click="$emit ('select', value)">
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>

  </div>
</template>

<script>
export default {
    data: function() {
        return{
            value: "",
        }
    }
}
</script>

<style>

</style>