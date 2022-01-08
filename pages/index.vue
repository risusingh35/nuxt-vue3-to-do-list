<template>
  <div>
    <div class="main">
      <Tutorial />
    </div>
    <About />
  </div>
</template>
<script>
// import HelloWorldVue from "./components/HelloWorld.vue";
export default {
  name: "App",
  components: {},
};
</script>
<style >
body {
  background-repeat: no-repeat;
  background-image: linear-gradient(
    to right top,
    #d16ba5,
    #c777b9,
    #ba83ca,
    #aa8fd8,
    #9a9ae1,
    #8aa7ec,
    #79b3f4,
    #69bff8,
    #52cffe,
    #41dfff,
    #46eefa,
    #5ffbf1
  );
}
.main {
  border-radius: 10px;
  border: none;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px,
    rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
  padding: 5%;

  margin: 2% 15%;
  padding: 2% 10% 5%;
}
</style>