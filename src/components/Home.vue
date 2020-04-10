<script src="../../../vue_shopee/src/main.js"></script>
<template>
    <div class="home_container">
      <el-container>
        <!--头部区域 放logo空间名之类的-->
        <el-header>
          <span>Welcome to our space❤</span>
          <a href="#" id="to_swc">happy 5/30</a>
        </el-header>
        <el-container>
          <el-aside width="200px">
            <el-menu
              default-active="2" unique-opened>
              <el-submenu :index="item.id+''" v-for="item in menuList" :key="item.id">
                <template slot="title">
                  <i :class="iconObj[item.id]"></i>
                  <span>{{item.menuTitle}}</span>
                </template>
                <el-menu-item-group v-for="subitem in item.submenu"
                                    :key="subitem.id">
                  <el-menu-item>
                    {{subitem.stitle}}
                  </el-menu-item>
                </el-menu-item-group>
              </el-submenu>
            </el-menu>
          </el-aside>
          <el-main>Main</el-main>
        </el-container>
      </el-container>
    </div>
</template>

<script>
export default {
  data () {
    return {
      menuList: [
        {
          id: 1,
          menuTitle: 'check ME',
          submenu: [
            {
              id: 101,
              stitle: '计算机网络'
            },
            {
              id: 102,
              stitle: 'CV of ME'
            },
            {
              id: 103,
              stitle: 'homework'
            },
            {
              id: 104,
              stitle: 'my update'
            }
          ]
        },
        {
          id: 2,
          menuTitle: 'to Sandwich',
          submenu: [
            {
              id: 201,
              stitle: 'music album'
            },
            {
              id: 202,
              stitle: 'piano toy'
            },
            {
              id: 203,
              stitle: 'typing game'
            },
            {
              id: 204,
              stitle: 'calm'
            }
          ]
        },
        {
          id: 3,
          menuTitle: "Let's doit",
          submenu: [
            {
              id: 301,
              stitle: 'share Routine and plan'
            },
            {
              id: 302,
              stitle: 'share Life'
            }
          ]
        }
      ],
      iconObj: {
        1: 'el-icon-s-opportunity',
        2: 'el-icon-service',
        3: 'el-icon-watch-1'
      }
    }
  }
}
</script>

<style lang="less" scoped>
  .home_container,
  .el-container{
    height: 100%;
  }
  .el-header {
    width: 100%;
    background-color: pink;
    font-size: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
