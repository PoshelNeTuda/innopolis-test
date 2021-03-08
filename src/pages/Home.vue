<template>
  <div class="home">
    <first-version class="home__version"/>
    <second-version class="home__version"/>
  </div>
</template>

<script>
import FirstVersion from '@/components/FirstVersion.vue'
import SecondVersion from '@/components/SecondVersion.vue'

export default {
  name: 'Home',
  components: {
    FirstVersion,
    SecondVersion
  }
}
</script>

<style lang="scss">
.home{
  display: flex;
  padding: 20px;

  &__version{
    &:not(:last-child){
      margin-right: 20px;
      padding-right: 20px;
      border-right: 10px solid black;
    }
  }
}
</style>
