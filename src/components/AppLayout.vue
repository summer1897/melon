<style scoped>
    #layout{
        border: 1px solid #d7dde4;
        /* border-right: 0px; */
        background: #f5f7f9;
        position: relative;
        border-radius: 4px;
        overflow: hidden;
    }
    .layout-header-bar{
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }

    .layout-logo-left{
        width: 90%;
        height: 30px;
        background: #5b6270;
        border-radius: 3px;
        margin: 15px auto;
    }
    .menu-icon{
        transition: all .3s;
    }
    .rotate-icon{
        transform: rotate(-90deg);
    }
    .menu-item span{
        display: inline-block;
        overflow: hidden;
        width: 69px;
        text-overflow: ellipsis;
        white-space: nowrap;
        vertical-align: bottom;
        transition: width .2s ease .2s;
    }
    .menu-item i{
        transform: translateX(0px);
        transition: font-size .2s ease, transform .2s ease;
        vertical-align: middle;
        font-size: 16px;
    }
    .collapsed-menu span{
        width: 0px;
        transition: width .2s ease;
    }
    .collapsed-menu i{
        transform: translateX(5px);
        transition: font-size .2s ease .2s, transform .2s ease .2s;
        vertical-align: middle;
        font-size: 22px;
    }
</style>
<template>
    <div id="layout">
        <Sider
          :style="{position: 'fixed', height: '100vh', left: 0, overflow: 'auto', border: '0px'}"
          ref="side1"
          hide-trigger
          collapsible
          :collapsed-width="78"
          v-model="isCollapsed"
          >
            <app-aside :class="menuitemClasses"/>
        </Sider>
        <Layout :style="{marginLeft: '200px'}">
          <Header :style="{padding: 0}" theme="dark" class="layout-header-bar">
              <!-- <Icon
                @click.native="collapsedSider"
                :class="rotateIcon"
                :style="{margin: '20px 20px 0'}"
                type="navicon-round"
                size="24"></Icon> -->
                <app-header/>
          </Header>
          <Content :style="{padding: '0 16px 16px'}">
              <Breadcrumb :style="{margin: '16px 0'}">
                  <BreadcrumbItem>Home</BreadcrumbItem>
                  <BreadcrumbItem>Components</BreadcrumbItem>
                  <BreadcrumbItem>Layout</BreadcrumbItem>
              </Breadcrumb>
              <Card>
                  <div style="height: 600px">Content</div>
              </Card>
          </Content>
        </Layout>
    </div>
</template>
<script>
    import AppAside from '@/components/AppAside'
    import AppHeader from '@/components/AppHeader'
    export default {
      name: 'app-layout',
      data() {
        return {
          isCollapsed: false
        };
      },
      computed: {
        rotateIcon () {
          return [
            'menu-icon',
            this.isCollapsed ? 'rotate-icon' : ''
          ];
        },
        menuitemClasses () {
          return [
            'menu-item',
            this.isCollapsed ? 'collapsed-menu' : ''
          ]
        }
      },
      methods: {
        collapsedSider () {
          this.$refs.side1.toggleCollapse();
        }
      },
      components: {
        AppAside,AppHeader
      }
    }
</script>
