<template>
  <div class="search">
    <input type="text" id="search-inp" v-model="keyword" />
    <button id="search-btn" @click="search">搜索</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      keyword: ""
    };
  },
  methods: {
    search() {
      this.$store.dispatch("searchValue", this.keyword).then(data => {
        if (data) {
          this.$toast(data);
        }
        // this.$toast(data);
      });
    }
  }
};
</script>

<style>
</style>