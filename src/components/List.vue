<!-- HTML -->
<template lang="html">
  <div class="view">
      <h1 class="title">{{title}}</h1>

      <input v-model="newStr" @keyup.enter="addData" />

      <ul>
        <li v-for="item in items" v-bind:class="{finish:item.isFinished}" @click="toggleFinish(item)">
          {{item.text}}
        </li>
      </ul>
  </div>
</template>

<!-- JS -->
<script>
export default {
  name: 'List',
  // data: function(){
  //   return{}
  // }
  data () {
    return {
      title: 'TodoList', // 標題
      items: [ // 代辦事項
        // {
        //   text:"今天晚上18:00跑步",
        //   isFinished: false
        // },
        // {
        //   text:"今天早餐",
        //   isFinished: true
        // },
      ],
      newStr: ''
    }
  },
  methods: {
    toggleFinish: function (item) {
      // 改變狀態
      item.isFinished = !item.isFinished
    },
    addData: function () {
      // console.log(this.newStr);
      this.items.push(
        {
          text: this.newStr,
          isFinished: false
        },
      );

      // 將輸入框中輸入 傳遞給 父組件 App
      // 觸發myMsg事件，並且傳遞參數
      this.$emit('myMsg', this.newStr)

      // 清空輸入框
      this.newStr = '';
    }
  }
}
</script>

<!-- CSS -->
<style lang="css" scoped>
    .view{
      width: 400px;
      border: 1px solid grey;
      margin: 20px auto;
    }

    .view .title{
      border-bottom: 1px solid gray;
    }

    .view ul li{
      margin: 10px 0;
      list-style: none;
    }

    .finish{
      color: grey;
      text-decoration: line-through;
    }

</style>
