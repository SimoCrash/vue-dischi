<template>
  <div>
    <HeaderPage @change="OnFiltersChange" />
    <MainPage :selectedValue="selectedValue" />
  </div>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';

export default {
  components: {
    HeaderPage,
    MainPage,
  },

  data() {
    return {
      selectedValue: 'none',
    }
  },
  
  methods: {
    OnFiltersChange(NewValue) {
      this.selectedValue = NewValue;
      console.log('sono NV= ' + NewValue);
      console.log('sono sV = ' + this.selectedValue);
    },
  },
}
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
</style>