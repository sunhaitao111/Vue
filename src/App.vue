
<template>
  <div id="app">
    <input type="text" v-model="text" class="text" placeholder="请输入列表文字">
    <button class="btn" @click="handleClick">提交</button>
    <ul class="todo-list">
      <li v-for="(item,index) in list" :key="index" @click="updata(index)">
        {{item}} <button class="btn" @click="removeItem(index)">删除</button>
      </li>
    </ul>
  </div>
   
</template>

<script>
export default{
  name:"app",
  data(){
    return({
      list: [
        "11111111111",
        "22222222222",
        "33333333333",
        "44444444444"
      ],
      text:''
    })
  },
  methods:{
    handleClick (){
      // console.log(this.text);
      this.list.push(this.text);
      // console.log(list.index)
      // Vue.set(this.list, this.selected, this.text);
      this.text=""
    },
    removeItem(index){
      this.list.splice(index,1)
    },
    updata(index){
      // this.selected = index; // 修改的位置
      this.text = this.list[index];
      
      // Vue.set(this.list, this.selected, this.text);
    }
  }
}

</script>

<style scoped>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2f129b;
  margin-top: 60px;
  list-style: none;
}
#app ul{
  list-style:none;
}
.btn{
  width: 75px;
  height: 33px;
  line-height: 33px;
  margin-left: 15px;
  text-align: center;
  border: 1px solid #cccccc;
  border-radius: 10px;
  background: #ffffff;
  color: #333;
  outline: none;  
}
.btn:hover{
  background: red;
  color: #ffffff;
  border: 1px solid forestgreen;
  cursor: pointer;
}
.text{
  width: 400px;
  height: 30px;
  color: #cccccc;
  font-size: 18px;
}
.todo-list{
  width: 500px;
  margin: 80px auto;
  background: rgb(182, 182, 182);
  box-shadow: #333 10px;
  border-radius: 10px;
  overflow: hidden;
}
.todo-list li{
  display: block;
  width: 90%;
  height: 40px;
  line-height: 40px;
  float: left;
  border-bottom: 1px solid skyblue;
}
.todo-list li .btn{
  float: right;
  margin-top: 2px;
}
</style>
