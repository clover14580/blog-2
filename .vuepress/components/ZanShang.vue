<template>
  <div id="zanshang">
    <div class="pay-wrap" v-if="show" :class="{'show': show}">
      <img src="https://res.oodcd.cn/zhi/wechatpay.png" class="wechat qrcode" alt="微信赞赏">
      <!-- <img src="https://res.oodcd.cn/zhi/alipay.png" class="alipay qrcode" alt="支付宝赞赏"> -->
      <p class="note">打赏，是最好的赞赏。</p>
    </div>
    <span class="zan-button" ref="button" @click="zan">微信赞赏作者</span>
  </div>
</template>
<script>
export default {
  data: () => ({
    show: false
  }),
  methods: {
    zan() {
      this.show = !this.show
      // if (this.show) { // 展开后该按钮是出现在视野中的
      //   this.$refs.button.scrollIntoView()
      // }
    }
  }
}
</script>
<style lang="stylus" scoped>
#zanshang {
  margin: 20px auto;
  text-align: center;
  position: relative;
  .pay-wrap {
    padding: 10px;
    position: absolute;
    transition: all ease 0.3s;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 2px;
    bottom: 50px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 0;
    &.show {
      visibility: visible;
      opacity: 1;
    }
    img {
      width: 220px;
      vertical-align: bottom;
      margin-top: 0;
      &.wechat {
        margin-right: 10px;
      }
      &:last-of-type{
        margin-right: 0px !important;
      }
    }
    .note {
      font-size: 14px;
      margin: 0;
    }
  }
  .zan-button {
    color: #fff;
    display: inline-block;
    border-radius: 4px;
    padding: 8px 20px;
    cursor: pointer;
    transition: all ease 0.3s;
    background-color: #FF5746;
    &:hover {
      background-color: darken(#FF5746, 10%);
    }
    &:active {
      background-color: darken(#FF5746, 20%);
    }
  }
}
</style>
