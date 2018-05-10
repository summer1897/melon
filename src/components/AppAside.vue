<style scoped>
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
  <Menu
    active-name="1-2"
    theme="dark"
    width="auto"
    :class="menuitemClasses"
    :open-names="['1']"
  >
      <Submenu name="1">
          <template slot="title">
              <Icon type="ios-navigate"></Icon>
              Item 1
          </template>
          <MenuItem name="1-1">Option 1</MenuItem>
          <MenuItem name="1-2">Option 2</MenuItem>
          <MenuItem name="1-3">Option 3</MenuItem>
      </Submenu>
      <Submenu name="2">
          <template slot="title">
              <Icon type="ios-keypad"></Icon>
              Item 2
          </template>
          <MenuItem name="2-1">Option 1</MenuItem>
          <MenuItem name="2-2">Option 2</MenuItem>
      </Submenu>
      <Submenu name="3">
          <template slot="title">
              <Icon type="ios-analytics"></Icon>
              Item 3
          </template>
          <MenuItem name="3-1">Option 1</MenuItem>
          <MenuItem name="3-2">Option 2</MenuItem>
      </Submenu>
      <Submenu name="4">
          <template slot="title">
              <Icon type="ios-analytics"></Icon>
              Item 4
          </template>
          <MenuItem name="4-1">Option 1</MenuItem>
          <MenuItem name="4-2">Option 2</MenuItem>
      </Submenu>
      <Submenu name="5">
          <template slot="title">
              <Icon type="ios-analytics"></Icon>
              Item 5
          </template>
          <MenuItem name="5-1">Option 1</MenuItem>
          <MenuItem name="5-2">Option 2</MenuItem>
      </Submenu>
      <Submenu name="6">
          <template slot="title">
              <Icon type="ios-analytics"></Icon>
              Item 6
          </template>
          <MenuItem name="6-1">Option 1</MenuItem>
          <MenuItem name="6-2">Option 2</MenuItem>
      </Submenu>
  </Menu>
</template>
<script>
  export default {
    name: 'app-aside',
    props: {
      isCollapsed: false
    },
    data() {
      return {
        msg: ''
      };
    },
    computed: {
      menuitemClasses () {
        console.log("is collapse: ",this.isCollapsed);
        return [
          'menu-item',
          this.isCollapsed ? 'collapsed-menu' : ''
        ]
      }
    },
    methods: {

    }
  }
</script>
