<template>
  <div class="layout">
    <Layout>
      <Header class="layout-header">
        <Menu mode="horizontal" theme="primary" active-name="gravida">
          <div class="layout-logo">
            <span style="font-size:22px;color:#fff;font-weight:bold; line-height:30px;">校园志愿</span>
            <!-- <img :src="logo" class="logo"> -->
          </div>
          <div class="layout-drop">
            <Dropdown style="margin-left: 20px;" placement="bottom-end" :transfer="true">
              <a href="javascript:void(0)" style="color:#fff;">
                欢迎您，{{userName}}
                <Icon type="ios-arrow-down"></Icon>
              </a>
              <DropdownMenu slot="list">
                <DropdownItem><a @click="modify=true">重置密码</a></DropdownItem>
                <DropdownItem><a @click="signOut">退出登录</a></DropdownItem>
              </DropdownMenu>
            </Dropdown>
          </div>
        </Menu>
      </Header>
      <Layout>
        <Sider hide-trigger :style="{ minHeight: '688px', minWidth: '190px'}">
          <Menu :theme="theme" active-name="1" width="auto">
            <MenuGroup title="内容管理">
              <MenuItem name="1">
                  <Icon type="md-document" />
                  文章管理
              </MenuItem>
              <MenuItem name="2">
                  <Icon type="md-chatbubbles" />
                  评论管理
              </MenuItem>
            </MenuGroup>
            <MenuGroup title="统计分析">
                <MenuItem name="3">
                    <Icon type="md-heart" />
                    用户留存
                </MenuItem>
                <MenuItem name="4">
                    <Icon type="md-leaf" />
                    流失用户
                </MenuItem>
            </MenuGroup>
          </Menu>
        </Sider>
        <slot></slot>
      </Layout>
    </Layout>
  </div>
</template>

<script>
export default {
  name: 'myLayout',
  data () {
    return {
      theme: 'dark',
      logo: '',
      modify: false,
      userName: '测试用户'
    }
  },
  methods: {
    signOut () {
    }
  }
}
</script>

<style>
.layout {
  position: relative;
  min-height: 100vh;
  background: #f5f7f9;
  overflow: hidden;
}
.layout-header {
  background: #58B957;
  margin: 0 -50px;
}

/* .ivu-layout-header {
  background: #58B957;
} */
.logo{
  display: block;
  width: 100px;
  height: 30px;
}
.layout-logo {
  width: 100px;
  height: 30px;
  background: #58B957;
  border-radius: 3px;
  float: left;
  position: relative;
  top: 5px;
  margin-left: 50px;
}
.layout-drop {
  position: absolute;
  right: 50px;
}
</style>
