<template>
  <div class="about">
    <h1>Chrome 调试示例</h1>
    <Paragraph v-for="item in list" :key="item.title" :info="item"></Paragraph>
  </div>
</template>
<script>
// @ is an alias to /src
import Paragraph from "@/components/Paragraph.vue";
export default {
  name: "Home",
  components: {
    Paragraph
  },
  data() {
    return {
      list: [
        {
          title: "1、日志保持",
          detail: "保存 重新加载页面之前或导航发生时 等所有log记录",
          imgUrl: require("@/assets/log.png")
        },
        {
          title: "2、事件监听器的断点",
          detail:
            "通常，当用户交互发生时会出现问题。捕捉这些事件来检查在交互中运行的位置和内容非常有帮助。幸运的是，我们可以通过访问 Sources 选项卡，用 Ctrl + P 打开一个 js 文件，并检查其中的相关事件",
          imgUrl: require("@/assets/event.png")
        },
        {
          title: "3、DOM 操作的断点",
          detail:
            "对于 DOM 操作也可以添加断点。通常可以断点在某节点接收到属性更改上，例如添加了某个 class 。在一个大型代码仓库中搜索相关代码将耗费大量时间，其实你可以简单地为元素添加一个断点，然后剩下的交给 DevTools 处理。",
          imgUrl: require("@/assets/domevent.png")
        },
        {
          title: "4、代码覆盖率",
          detail: `有时候我们对代码进行性能优化，会导致很多代码没有用了但是还没及时清除。在覆盖工具的帮助下，你可以分析资源并查看哪些行没有执行。如果你关注的不是所有交互，只执行你所关注的交互操作有助于你获取准确的覆盖率。你可以点击 Ctrl + Shift + P 打开工具面板，输入coverage 选择“Show Coverage”，然后点击重新加载图标开始记录，所有以红色显示的内容都不会被执行。`,
          imgUrl: require("@/assets/coverage.png")
        },
        {
          title: "5、黑盒",
          detail:
            "将 Vue、React、jQuery等核心框架js关进黑盒，DevTools 将跳过这些文件，也就是断点不进这些内部框架。 Ctrl + Shift + P 打开工具面板，输入black 选择“Show Blackbboxing，进行设置。",
          imgUrl: require("@/assets/blackbox.png")
        },
        {
          title: "6、Lighthouse",
          detail:
            " Lighthouse 面板，这是为了审计你的网站在各种指标：性能，PWA，可访问性，或搜索引擎优化。你还可以选择审计不同的设备以及模拟网络连接，它为你提供了哪些可以改进以及如何改进的参考。你可以在“Audits” 选项卡下进入“灯塔”，如果你没有看到标签，只需点击锯齿符号来显示隐藏的标签。生成报告后，可以将结果保存为 JSON 文件，稍后导入以进行比较。",
          imgUrl: require("@/assets/lighthouse.png")
        }
      ]
    };
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
