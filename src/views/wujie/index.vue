<!-- my-page.vue -->
<template>
  <div>
    <h1>子应用</h1>
    <!-- <WujieVue
      width="100%"
      height="100%"
      style="padding-left: 6rem; padding-right: 2rem"
      :name="appName"
      :url="appUrl"
    ></WujieVue> -->
    <WujieVue
      width="100%"
      height="100%"
      name="vite"
      :url="viteUrl"
      :sync="true"
    ></WujieVue>

    <!--
      name(必传)：应用名称
      url(必传)：应用地址，会被自动补全为http://localhost:3000/index.html
      baseroute(可选)：基座应用分配给子应用的基础路由，就是上面的 `/my-page`
     -->
    <!-- <micro-app
      name="vue3-vite"
      url="http://localhost:4001/vue3-vite/"
      inline
      disableSandbox
      baseroute="/vue3-vite"
      :data="mainViteValue"
      @created="handleCreated"
      @mounted="handleMount"
      @unmount="unmount"
      @datachange="handleDataChange"
    ></micro-app> -->
  </div>
</template>
<script>
export default {
  data() {
    return {
      viteUrl: "//localhost:8080/#/login"
    };
  }
};
// import { getCurrentAppEntry } from "@/utils/app"
// const appUrl = ref("")
// const appName = "app1"
// appUrl.value = getCurrentAppEntry(appName)
// import { EventCenterForMicroApp } from "@micro-zoe/micro-app"
// import { ref } from "vue"

// const mainViteValue = ref({})

// const handleCreated = () => {
//   // 注意：每个vite子应用根据appName单独分配一个通信对象
//   window.eventCenterFor_vue3Vite = new EventCenterForMicroApp("vue3-vite")
//   // console.log('vue3-vite 已经渲染完成')
//   mainViteValue.value = { token: 123455678 }
// }

// const handleMount = () => {
//   console.log(12312)
// }

// const unmount = () => {
//   console.log(39, window["vue3-vite"])
//   window["vue3-vite"].unmount()
//   // window.dispatchEvent(new Event('unmount-bakingVue'))
// }
// const handleDataChange = (e) => {
//   console.log("来自子组件vue3-vite的数据", e.detail.data)
// }
</script>
