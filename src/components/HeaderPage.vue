<template>
  <div>
    <div class="h-70 d-flex justify-content-between header-bg">
        <img src="@/components/img/logo-small.svg" alt="">
        <select v-model="value" @change="$emit('change', value)">
          <option value="none"></option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
          <option value="Metal">Metal</option>
        </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderPage",
  data(){
    return {
      value: "none",
    }
  },
}
</script>

<style lang="scss" scoped>
    .header-bg {
        background-color: #2E3A46;
        img, select {
            height: 60px;
            margin: 10px 20px;
        }
    }
</style>