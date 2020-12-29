<template>
  <select id="selectCardStatus">
    <option v-for="status in cardStatus">
      {{status}}
    </option>
  </select>
</template>

<script>
export default {
props:['cardStatus']
}
</script>

<style scoped>

</style>
