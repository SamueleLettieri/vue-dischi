<template>
  <div class="text-center p-5"> 
    <select v-model="value" @click="$emit ('select', value)">
        <option value="">Tutti</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
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