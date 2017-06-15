<template>
  <div style="{backgroundColor: transparent, height: 356 }">
    <div class="item-container" @click="detailClick">
      <image class="item-pic" :src="pic" />
      <div class="item-info">
        <div>
          <text class="title">{{title}}</text>
          <text class="shop">{{shop}}</text>
        </div>
        <div class="bottom">
          <div class="buy-info">
            <text class="price">￥{{price}}</text>
            <text class="sold">销量{{sold}}笔</text>
          </div>
          <text class="buy" @click="buyClick">Add</text>
        </div>
      </div>
    </div>
    <div class="footer">
      <fbar></fbar>
    </div>
  </div>
</template>

<style>
  .item-container {
    width: 750;
    height: 276;
    padding-top: 24;
    padding-left: 30;
    padding-right: 30;
    padding-bottom: 24;
    background-color: #ffffff;
    flex-direction: row;
  }
  .item-pic {
    width: 216;
    height: 216;
  }
  .item-info {
    width: 454;
    height: 216;
    margin-left: 20;
    flex-direction: column;
    justify-content: space-between;
  }
  .title {
    font-size: 28;
    font-weight: bold;
    color: #333333;
  }
  .shop {
    font-size: 24;
    color: #999999;
    margin-top: 10;
  }
  .bottom {
    width: 454;
    flex-direction: row;
    align-items: flex-end;
    justify-content: space-between;
  }
  .buy-info {
    flex-direction: row;
    align-items: flex-end;
  }
  .price {
    color: #f40000;
    font-size: 28;
    font-weight: bold;
  }
  .sold {
    margin-left: 10;
    font-size: 28;
    color: #999999;
  }
  .buy {
    width: 80;
    height: 80;
    color: #ffffff;
    font-size: 40;
    background-color: #f40000;
    text-align: center;
    padding-top: 16;
    border-radius: 40;
  }
  .footer {
    width: 750;
    height: 100;
  }
</style>

<script>
  var userTrack = weex.requireModule('userTrack');
  // var fbar = require('./footer-bar.vue');
  import fbar from './footer-bar.vue'
  var local = require('./local.js');
  module.exports = {
    components: {
      fbar: fbar
    },
    created: function() {
      console.info('Lifecycle created.');
      console.warn('local.js: ' + local.message());
    },
    props: {
      title: {
        default: "COCOON/可可尼2017夏装新品甜美彩绘印花无袖修身连衣裙"
      },
      itemId: {
        default: 545194660752
      },
      shop: {
        default: "测试旗舰店"
      },
      pic: {
        default: "https://img.alicdn.com/bao/uploaded/i1/468333872/TB2ZpPse8NkpuFjy0FaXXbRCVXa_!!468333872.jpg_b.jpg"
      },
      sold: {
        default: "1050"
      },
      price: {
        default: "102.0"
      }
    },
    methods: {
      detailClick: function (url) {
        var nav = weex.requireModule('event');
        if (nav && nav.openURL) {
          nav.openURL("tmall://page.tm/itemDetail?itemId=" + this.itemId);
        } else {
          console.error('navigator module is not valid.');
        }
      },
      buyClick: function() {
        console.info('Add cart click.');
        var modal = weex.requireModule('modal');
        modal.toast({message: "Add click.", duration: 0});
      }
    }
  };
</script>
