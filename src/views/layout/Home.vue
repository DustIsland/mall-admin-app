<template>
  <div class="home">
    <div class="menu-list">
      <a-menu
        :default-selected-keys="['1']"
        :default-open-keys="['sub1']"
        mode="inline"
        theme="dark"
        :inline-collapsed="collapsed"
      >
        <a-sub-menu key="sub1">
          <span slot="title"><a-icon type="home" /><span>首页</span></span>
          <a-menu-item key="5"> <a-icon type="transaction" />统计 </a-menu-item>
        </a-sub-menu>
        <a-sub-menu key="sub2">
          <span slot="title"
            ><a-icon type="shopping-cart" /><span>商品</span></span
          >
          <a-menu-item key="9"> 商品列表 </a-menu-item>
          <a-menu-item key="10"> 添加商品 </a-menu-item>
        </a-sub-menu>
      </a-menu>
    </div>
    <div :class="{ 'main-app': true, 'menu-unfold': collapsed }">
      <div class="main-header">
        <a-button
          type="primary"
          style="margin-bottom: 16px"
          @click="toggleCollapsed"
        >
          <a-icon :type="collapsed ? 'menu-unfold' : 'menu-fold'" />
        </a-button>
        <div class="breadcrumb">
          <a-breadcrumb>
            <a-breadcrumb-item>首页</a-breadcrumb-item>
            <a-breadcrumb-item><a href="#">统计</a></a-breadcrumb-item>
          </a-breadcrumb>
        </div>
        <ul class="user-info">
          <li>欢迎米八<a-icon type="down" /></li>
          <li>退出登录</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      collapsed: false,
    };
  },
  methods: {
    toggleCollapsed() {
      this.collapsed = !this.collapsed;
    },
  },
};
</script>

<style lang="less">
@import url("~@/assets/css/home.less");
@import url("~@/assets/css/reset.less");
</style>
