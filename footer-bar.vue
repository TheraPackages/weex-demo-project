<template>
  <div class="footer-container" @click="footerClick">
    <text class="footer-desc">Desc: Tap to test third party dependency.</text>
    <text class="tooter-tip">npm install demo-tool</text>
  </div>
</template>

<style>
.footer-container {
  width: 750;
  height: 80;
  background-color: #eeeeee;
  justify-content: center;
  padding-left: 20;
}
.footer-desc {
  color: #333333;
  font-size: 32;
}
.tooter-tip {
  color: #999999;
  font-size: 24;
}
</style>

<script>
var tool = require('demo-tool');
module.exports = {
  created: function() {
    console.info("Footer created.");
  },
  methods: {
    footerClick: function() {
      var footDesc = tool.name() + " in " + tool.company() + ".";
      console.info(footDesc);

      var modal = weex.requireModule("modal");
      modal.toast({message: footDesc, duration: 0});
    }
  }
}
</script>
