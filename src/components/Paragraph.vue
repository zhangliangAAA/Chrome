<template>
  <div class="para">
    <h3>{{ info.title }}</h3>
    <p>{{ info.detail }}</p>
    <img alt="Vue logo" :src="info.imgUrl" />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    info: {
      type: Object,
      default: () => {
        return {
          title: "标题",
          detail: "",
          imgUrl: ""
        };
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.para {
  text-align: left;
}
img {
  width: 500px;
}
</style>
