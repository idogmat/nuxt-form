<template>
  <div>
    <SecondNav></SecondNav>
    {{this.$route.path}}
  </div>
</template>
<script>
import SecondNav from '@/components/secondNav'
export default {
  components:{
    SecondNav
  }
}
</script>
