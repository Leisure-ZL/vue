<template>
    <div class="container">
      <div class="top">
        <div class="leftInput">
          <a-input v-model="inputVal"></a-input>
        </div>
        <div class="right">
          <a-button @click="handleClick">添加</a-button>
        </div>
      </div>
  
      <div class="body">
        <a-list item-layout="horizontal" :data-source="filterList">
          <a-list-item slot="renderItem" slot-scope="vaule">
            <a-checkbox :checked="vaule.done" @change="(e)=>handleToggle(e, vaule)">
              {{vaule.todoMessage}}
            </a-checkbox>
            <a slot="actions" @click="()=>{handleDelete(vaule.id)}">删除</a>
          </a-list-item>
          <a-button-group>
            <a-button :type="key== 'all' ? 'primary': 'default'" @click="changeList('all')">所有</a-button>
            <a-button :type="key== 'finished' ? 'primary': 'default'" @click="changeList('finished')">已完成</a-button>
            <a-button :type="key== 'unFinished' ? 'primary': 'default'" @click="changeList('unFinished')">未完成</a-button>
          </a-button-group>
        </a-list>
      </div>
    </div>
  </template>
  
  <script>
  
  export default {
    data () {
      return {
        inputVal: '',
        items: [],
        key: 'all'
      }
    },
    mounted () {
      this.$axios.get('./data.json').then((res) => {
        console.log(res)
        console.log(res.data)
        this.items = res.data.items
      })
    },
    computed: {
      size () {
        return this.items.length
      },
      filterList () {
        switch (this.key) {
          case 'all':
            return this.items
          case 'unFinished':
            return this.items.filter(e => {
              return !e.done
            })
          case 'finished':
            return this.items.filter(e => {
              return e.done
            })
          default:
            return this.items
        }
      }
    },
    methods: {
      changeList (value) {
        this.key = value
      },
      handleClick () {
        const len = this.items.length
        this.items.push({
          id: len + 1,
          todoMessage: this.inputVal
        })
      },
      handleDelete (id) {
        console.log(id)
        const index = this.items.findIndex(e => {
          return e.id === id
        })
        console.log(index)
        this.items.splice(index, 1);
      },
      handleToggle (e, value) {
        console.log('handleToggle', e, value)
        const index = this.items.findIndex(e => {
          return e.id === value.id
        })
        console.log('object', value, { ...value, done: !value.done })
        this.items.splice(index, 1, { ...value, done: !value.done });
  
      }
    }
  }
  </script>
  
  <style lang="less" scoped>
  .container {
    width: 500px;
    margin:  0 auto;
  }
    .top {
      padding: 10px 0;
      display: flex;
    }
      .leftInput {
        flex: auto;
      }
      .right {
        flex: 0 0 100px;
      }
  
  </style>
  