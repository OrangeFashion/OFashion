##This project was generated with webpack.##

* **项目介绍：**
 * 产品内容介绍/次元仓
 *
  动漫周边

  动漫周边是以动漫为主题，囊括了当前热门的动漫以及即将上线的动漫周边产品，虚拟与现实的结合，让消费者对动漫的喜好延续到了现实。
  游戏周边
 游戏周边是以游戏为主题，在次元仓，消费者可以买到游戏人物的服装道具，把游戏搬进现实。

 * Cosplay
 在cosplay频道，次元仓会及时更新和呈现一批又一批热门的服装和道具。百里屠苏的剑、古装里的面纱、还有日本各式各样的和服等。
 * 古风仓
 古风仓会提供古风系列的产品，二次元用户可以在里面挑选自己的商品。
 * 秒杀仓
 秒杀仓会限时提供一些商品，这些商品会以最优惠的价格出售，最低半价出售。
 * 投票榜
 消费者在投票榜对自己喜欢的商品进行投票，商品的预售跟消费者的投票数息息相关。


* **本项目主要用到的工具和技术**
 1.  用webpack实现的模块化开发
 2.  前端模板YO
 3.  数据渲染vue.js
 4.  还用到了vuex进行全局变量的定义以及控制
 5.  针对vue的特点自定义了指令
 6.  还用到了IScroll和Swiper实现滑动效果

* **APP路由**
     router.map({
       '/': {
         component: guide,
       },
       //配置子路由 ，“/”是自动进入的路由页面
       '/index': {
         component: index,
         subRoutes: {
           '/': {
             component: main
           },
           '/buy': {
             component: buy
           },

           '/classifyBox': {
             component: classifyBox,
             subRoutes: {
               '/': {
                 component: classify,
                 subRoutes: {
                   '/': {
                     component: classifySkirt
                   },
                   "/classifyJacket": {
                     component: classifyJacket
                   },
                   "/classifyPants": {
                     component: classifyPants
                   },
                   "/classifyCoat": {
                     component: classifyCoat
                   },
                   "/classifyParts": {
                     component: classifyParts
                   },
                   "/classifyBag": {
                     component: classifyBag
                   },
                   "/classifyAttire": {
                     component: classifyAttire
                   },
                   "/classifyHome": {
                     component: classifyHome
                   },
                   "/classifyStationery": {
                     component: classifyStationery
                   },
                   "/classifyNumeral": {
                     component: classifyNumeral
                   },
                   "/classifyPlay": {
                     component: classifyPlay
                   }
                 }
               }
             }
           },
           '/label': {
             component: label
           }
         }
       },
       '/my': {
         component: my
       },
       '/list': {
         component: list
       },
       '/detail': {
         component: detail
       },
       '/person/:zhanghao': {
         component: person
       },
       '/login/:zhanghao': {
         name: 'login',
         component: login
       },
       '/zhuce': {
         component: zhuce
       },
       '/bianji/:zhanghao': {
         name: 'bianji',
         component: bianji
       },
       '/dingdan/:id': {
         name: 'dingdan',
         component: dingdan
       }
     });
