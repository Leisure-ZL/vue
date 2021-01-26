<template>
    <a-layout id="components-layout-demo-custom-trigger">
      <a-layout-sider v-model="collapsed" :trigger="null" collapsible :theme="theme">
        <div class="logo">
            <a-icon
            class="trigger"
            :type="collapsed ? 'menu-unfold' : 'menu-fold'"
            @click="triggerDisp"
          />
          <a-switch 
          class="switch"
          checked-children="dark"
          un-checked-children="light"
          :style="{display: controlDisp}"
          @change="changeTheme" />
        </div>
        <a-menu :theme="theme" mode="inline" :default-selected-keys="['1']">
          <a-menu-item key="1">
            <a-icon type="user" />
            <span>nav 1</span>
          </a-menu-item>
          <a-menu-item key="2">
            <a-icon type="video-camera" />
            <span>nav 2</span>
          </a-menu-item>
          <a-menu-item key="3">
            <a-icon type="upload" />
            <span>nav 3</span>
          </a-menu-item>
          <a-menu-item key="4">
            <a-icon type="upload" />
            <span>nav 4</span>
          </a-menu-item>
          <a-menu-item key="5">
            <a-icon type="upload" />
            <span>nav 5</span>
          </a-menu-item>
          <a-menu-item key="6">
            <a-icon type="upload" />
            <span>nav 6</span>
          </a-menu-item>
        </a-menu>
      </a-layout-sider>
      <a-layout>
        <a-layout-header :style="{ backgroundColor: controlColor}">
          this is the head
        </a-layout-header>
        <a-layout-content
          :style="{backgroundColor: controlColor ,minHeight: '660px'}"
          class="content"
        >
          Content
        </a-layout-content>
      </a-layout>
    </a-layout>
  </template>
  <script>
  export default {
    data() {
      return {
        collapsed: false,
        theme: 'light',
        controlDisp: '',
        controlColor: 'white'
      };
    },
    methods: {
        changeTheme: function(checked) {
            this.theme = checked ? 'dark' : 'light';
            this.controlColor = checked ? 'black' : 'white';
        },
        triggerDisp: function() {
            this.collapsed = !this.collapsed;
            this.controlDisp = this.collapsed ? 'none' : ''
        },
        
    }
  };
  </script>
  <style>
  #components-layout-demo-custom-trigger .trigger {
    font-size: 20px;
    line-height: 32px;
    padding: 0 12px;
    cursor: pointer;
    transition: color 0.3s;
  }
  
  #components-layout-demo-custom-trigger .trigger:hover {
    color: #1890ff;
  }
  
  #components-layout-demo-custom-trigger .logo {
    height: 22px;
    background: rgba(255, 255, 255, 0.959);
    margin: 16px;
  }

  #components-layout-demo-custom-trigger .switch {
    margin: 0 0 12px 20px;
  }

  #components-layout-demo-custom-trigger .content {
    margin: '24px 16px';
     padding: '24px';
    background: '#fff';
     
  }
  
  </style>
  