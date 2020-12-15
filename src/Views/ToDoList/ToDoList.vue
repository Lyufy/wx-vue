<template>
  <el-container>
    <el-header class="header-class">我的待办</el-header>
    <el-main>
      <el-input placeholder="请输入内容" v-model="input" clearable> </el-input>
      <el-button type="primary" @click="clickBtn">添加待办</el-button>
      <el-tag
         v-for="(item,index) in tags"
          :key="item.name"
          closable
          :type="item.type"
          @close="clickToDel(index)">
          {{item.name}}
      </el-tag>
    </el-main>
  </el-container>
</template>

<script>
export default{
  name: 'ToDoList',
  data () {
    return {
      input: '',
      typeIndex: 0,
      typeStrs: ['', 'success', 'info', 'warning', 'danger'],
      tags: [
      ]
    }
  },
  methods: {
    clickToDel (index) {
      this.tags.splice(index, 1)
    },
    clickBtn () {
      let content = {
        name: this.input,
        type: this.typeStrs[this.tags.length % 5]
      }
      this.tags.push(content)
    }
  }
}
</script>

<style scoped>
.el-header {
  text-align: center;
}
.el-button{
  display: block;
  margin: 20px auto 20px auto;
}
.header-class{
  font-family: "微软雅黑"
}
</style>
