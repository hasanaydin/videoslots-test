<template>
  <div class="footer-filter">
    <select
      @change="filterImage"
      class="footer-filterOption"
      v-model="activeAuthor"
    >
      <option value="all" selected>All Authors</option>
      <option v-for="author in authorList" :key="author" :value="author">
        {{ author }}
      </option>
    </select>
  </div>
</template>
<script>
export default {
  name: "PhotoListFilter",
  props: {
    image: Object,
    authorList: Array,
  },
  data() {
    return {
      imageList: null,
      activeAuthor: "all",
    };
  },
  methods: {
    filterImage() {
      this.$emit("select", this.activeAuthor);
    },
  },
};
</script>
