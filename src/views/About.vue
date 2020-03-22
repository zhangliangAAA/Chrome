<template>
  <div class="home">
    <h1>Chrome 调试示例</h1>
    <img class="icon" alt="Vue logo" src="@/assets/chrome.jpg" @click="say" />
    <div class="dom">
      <button @click="operateDom">操作dom</button>
    </div>
    <div>
      <button @click="gotoAbout">黑盒测试（过滤掉Vue内部）</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {
    // HelloWorld
  },
  mounted() {
    console.log("Home mounted");
  },
  methods: {
    say() {
      console.log("Hello");
    },
    operateDom() {
      document
        .getElementsByClassName("dom")[0]
        .appendChild(document.createTextNode("操作dom加上的信息"));
    },
    noUse() {
      console.log("无用的代码");
    },
    gotoAbout() {
      this.$router.push({
        path: "/about"
      });
    }
  }
};
</script>
<style lang="scss" scoped>
.home {
  .icon {
    width: 100px;
  }
}
</style>
