<template>
  <div class="text-center p-5"> 
    <select v-model="value" @click="$emit ('select', value)">
        <option value="">Tutti</option>
        <option value="Bon Jovi">Bon Jovi</option>
        <option value="Queen">Queen</option>
        <option value="Sting">Sting</option>
        <option value="Steve Gadd Band">Steve Gadd Band</option>
        <option value="Iron Maiden">Iron Maiden</option>
        <option value="Eric Clapton">Eric Clapton</option>
        <option value="Deep Purple">Deep Purple</option>
        <option value="Metallica">Metallica</option>
        <option value="Dave Weckl">Dave Weckl</option>
        <option value="Michael Jacjson">Michael Jacjson</option>
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