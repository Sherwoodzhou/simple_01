<template>
    <div>
      <button v-on:click="run1()">方法一</button>
      <button @click="run2()">方法二</button>
      <button @click="setMsg()">数据+1</button>
      <button @click="getMsg()">获取数据</button>
      {{msg}}
    </div>
</template>

<script>
  export default {
    name: 'RunFunction',
    data(){
      return{
        msg: 1,
        list:[]
      }
    },methods: {
      run1(){
        alert('这是方法一');
      },
      run2(){
        alert('这是方法二');
      },getMsg(){;
        alert(this.msg);
      },setMsg(){
        this.msg +=1;
      },requestData(){
        for (var i=0;i<10;i++){
          var len = list.length+1;
          this.list.push('我是第'+len+'数据')
        }
      }
    }
  }
</script>

<style scoped>

</style>
