<template>
  <div id="app">
    <!--    <img src="./assets/logo.png">
        <router-view/>-->
    <h1>数据显示</h1>
    <hr/>
    <ul>
      <li v-for="item in list">
        {{item}}
      </li>
    </ul>
    <hr/>
    <ul>
      <li v-for="item in list2">
        {{item.title}}
      </li>
    </ul>
    <ul>
      <li v-for="item in list3">
        {{item.cate}}
        <ol>
          <li v-for="news in item.list">
            {{news.title}}
          </li>
        </ol>
      </li>
    </ul>
    <hr/>
    <h1>数据绑定</h1>
    <div v-bind:title="title">这里是上海</div>
    <div v-bind:class="{'red': flag}">绑定class</div><!--'red'是我们的类，冒号后面是true还是false，也可以是一个判断语句-->
    <hr/>
    <div v-bind:class="{'blue': flag}">蓝色的class</div>
    <h1>双向绑定</h1>
    <form>
      <h3>{{msg}}</h3>
      <input type="text" v-model="msg"/>
      <h1>绑定方法</h1>
      <button v-on:click="getMsg()">获取表单中的数据</button>
      <button v-on:click="setMsg()">我是修改后的</button>
    </form>
    <hr/>
    <input type="text" ref="userinfo" />
    <div ref="box">这里会显示什么颜色</div>
    <button v-on:click="getInputValue">获取输入值</button>
  </div>

</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      flag: true,
      title: '这里是中国',
      /*键值对*/
      msg: '互相修改',
      /*对象*/
      obj: {
        name: 'zhangs'
      },
      /*列表*/
      list: ['111', '2222', '333'],
      list2: [/*列表中包含键值对*/
        {'title': '111'},
        {'title': '222'},
        {'title': '333'}
      ],
      list3: [
        {
          "cate": "国内新闻",
          "list":[
            {'title': '北京新闻'},
            {'title': '上海新闻'}
          ]
        },{
          "cate": "国际新闻",
          "list":[
            {'title': '欧洲新闻'},
            {'title': '东南亚新闻'}
          ]
        }
      ]
    }
  },methods:{/*放方法的地方*/
    getMsg(){
      alert('vue方法执行了');
      alert(this.msg);
    },
    setMsg(){
      this.msg='我是修改后的数据';
    },getInputValue(){
      //获取ref定义的dom节点
      console.log(this.$refs.userinfo);

      this.$refs.box.style.background='red';
      alert(this.$refs.userinfo.value);
    }
  }
}
</script>

<style>
/*  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }*/
  .red{
    color: red;
  }
  .blue{
    color: blue;
  }
</style>
