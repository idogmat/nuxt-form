<template>
<div>
  <select id="selectCardType">
    <option v-for="type in cardType">
      {{type}}
    </option>
  </select>
</div>
</template>

<script>
export default {
props:['cardType']
}
</script>

<style scoped>

</style>
