<template>
  <!-- <div id="my-scroll"> -->
    <div class="my-container" >
    <!--头部  -->
    <header>
      <div class="header-tpo">
        <div class="touxiang" v-on:click="ziliao"><img src="/images/user_icon.png"  alt=""/></div>
        <div class="header-name"><p>{{nicheng}}</p></div>
      </div>
    </header>
    <!--内容  -->
    <section>
      <!--我的订单  -->
      <div class="dingdan">

        <div class="dingdan-top"  v-link="{name:'dingdan',params:{id: 0}}">
          <span>我的订单</span>
          <a href="#">查看全部订单<i></i></a>
        </div>

        <ul class="fukuan">
          <li v-for="li in list" v-link="{name:'dingdan',params:{id: li.id}}">
            <i>
              <img v-bind:src="li.img" alt="" />
              <p>{{li.name}}</p>
            </i>
          </li>

        </ul>
      </div>

      <!--收货地址等  -->
      <div class="my">
        <ul>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
        </ul>
      </div>

      <!--邀请  -->
      <div class="kefu">
        <ul>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
          <li>
            <a href="#">
              <span></span>
              <p>
                我的收藏
              </p>
            </a>
          </li>
        </ul>
      </div>
      <!-- 退出登录 -->
      <div class="exit"></div>
    </section>
  <!-- </div> -->
  </div>
</template>
<script>
var Vue = require('../libs/vue.js');
var VueResource = require('../libs/vue-resource.js');
var VueRouter=require('../libs/vue-router');
Vue.use(VueRouter);
Vue.use(VueResource);
  export default{
    data(){
      return{
        list:[],
        nicheng:'',
        username:''
      }
    },
    ready: function(){
      var zhanghao=this.$route.params.zhanghao;
      this.username=zhanghao;
      console.log(zhanghao);
      this.nicheng=JSON.parse(localStorage.getItem(zhanghao)).nicheng;
      var that =this;
      this.$http.get('/mock/my-lsit.json')
      .then((res)=>{
        that.list=res.data.data;
        console.log(res.data.data);
      });

    },
    methods:{
      ziliao:function(){
      this.$router.go({path:'/person',params:{zhanghao:this.username}});
      }
    }
  }
</script>
