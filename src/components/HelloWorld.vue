<template>
  <div class="toutu">
    <div :class="searchBarFixed == true ? 'isFixed' :'tou'">
      <sapn class="logo"> </sapn>
      <ul class="biao">
        <li><a href="#">主页</a></li>
        <li><a href="#introduce">文章</a></li>
        <li><a href="#">留言版</a></li>
        <li><a href="#">友链</a></li>
        <li><a href="#">关于</a></li>
      </ul>
    </div>

    <div :class="maintextdisplay==false? 'notoututext':'toututext'">
      <h1>
        Even&nbsp;if&nbsp;you&nbsp;go&nbsp;we'll&nbsp;find&nbsp;our&nbsp;way...
      </h1>
    </div>

    <div class="main">
      <div class="touxiang">
        <el-avatar :size="168" :src="circleUrl"></el-avatar>
      </div>
      <div class="mainmin">
        <h1>human</h1>
        <h5>"find&nbsp;our&nbsp;way"</h5>
        <a href="">more..</a>
      </div>

      <div class="mainleftone">
        <a href="">{{ num }}</a>
        <div>文章</div>
      </div>
      <div class="mainlefttwo">
        <a href="">{{ num }}</a>
        <div>动态</div>
      </div>
      <div class="mainright">
        <el-tooltip content="听我的歌" placement="bottom" effect="light">
          <button class="rightbutton">
            <i class="el-icon-chat-dot-square"></i>
          </button>
        </el-tooltip>
        <el-tooltip content="听我的歌" placement="bottom" effect="light">
          <button class="rightbutton"><i class="el-icon-headset"></i></button>
        </el-tooltip>
        <el-tooltip content="听我的歌" placement="bottom" effect="light">
          <button class="rightbutton"><i class="el-icon-picture"></i></button>
        </el-tooltip>
        <el-tooltip content="听我的歌" placement="bottom" effect="light">
          <button class="rightbutton"><i class="el-icon-share"></i></button>
        </el-tooltip>
      </div>
    

      <div id="introduce">
        <div class="introduceleft" id="Ashadow"></div>
        <div class="introduceright">
          <div class="introducerightone" id="Ashadow"></div>
          <div class="introducerighttwo" id="Ashadow"></div>
        </div>
      </div>

      <div class="bigtext">
        <h1>最近发布</h1>
      </div>

      <div class="newarticle">
        <div class="article"  v-for="item in article" :key="item.index">
          <div class="articleleft">
            <img src="" alt="" class="articleimg" />
          </div>
          <div class="articleright">
            <h2>{{item.articletitle}}</h2>
            <div class="articleintro">
              <p>{{item.articlecontent}}</p>
            </div>
            <div class="articledate">
              <i class="el-icon-edit-outline"></i>
              {{item.articledate}}
            </div>
          </div>
        </div>

        <div class="mystate"  v-for="item in mystat">
          <div class="mystatetouxiang">
            <el-avatar :size="70" :src="circleUrl" ></el-avatar>
            <div class="mystatetop">
              <h3>{{item.mystatname}}</h3>
              <p>{{item.mystattime}}</p>
            </div>
          </div>
          <div class="mystatecontent">
            <h4>{{item.mystatecontent}}</h4>
          </div>
        </div>


        <div class="bigtext">
          <h1 class="moretext">查看更多→</h1>
        </div>
      </div>

      <div class="mainbottom">
        Developed by human | Copyright © 2021-2022 本博客仅作为自己日常记录使用
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      maintextdisplay:true,
      searchBarFixed:false,
      num: 7,
      circleUrl:
        "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fi0.hdslb.com%2Fbfs%2Farticle%2F29373c59596f7d98e72f873a9671628e05eb18cd.jpg&refer=http%3A%2F%2Fi0.hdslb.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1667559985&t=dd19f8e0f87f6bb692026c80e5ad76a1",
        article:[
          {
            articletitle:"这是第一篇文章",
            articlecontent:"镜头之下，文章身穿一件白衬衣，手拿话筒发言，说起话来还是幽默又大方，只是他和大家记忆中的模样已经截然不同了，最明显的就是文章的脸胖了一大圈，还有点发腮，当他笑起来的时候，脸上的皱纹更是十分明显，不得不承认，才38岁的他，真的不像是38岁的模样，显得十分沧桑。",
            articledate:"2022.10.06 12:00",
          },
          {
            articletitle:"这是第2篇文章",
            articlecontent:"镜头之下，文章身穿一件白衬衣，手拿话筒发言，说起话来还是幽默又大方，只是他和大家记忆中的模样已经截然不同了，最明显的就是文章的脸胖了一大圈，还有点发腮，当他笑起来的时候，脸上的皱纹更是十分明显，不得不承认，才38岁的他，真的不像是38岁的模样，显得十分沧桑。",
            articledate:"2022.10.06 12:00",
          },
        ],
        mystat:[
          {
            mystatname:"human",
            mystattime:"2022.10.06 13:00",
            mystatecontent:"这是我的第一条动态"
          },
          {
            mystatname:"human",
            mystattime:"2022.10.06 13:00",
            mystatecontent:"镜头之下，文章身穿一件白衬衣，手拿话筒发言，说起话来还是幽默又大方，只是他和大家记忆中的模样已经截然不同了，最明显的就是文章的脸胖了一大圈，还有点发腮，当他笑起来的时候，脸上的皱纹更是十分明显，不得不承认，才38岁的他，真的不像是38岁的模样，显得十分沧桑。"
          },
        ]
    };
  },


  mounted () {
    // 监听鼠标滚动事件
  window.addEventListener('scroll', this.handleScroll)
},
methods:{
  handleScroll () {
  var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
  console.log(scrollTop)
  if (scrollTop >1) {
    this.searchBarFixed = true 
  } else {
    this.searchBarFixed = false
  }
  if(scrollTop > 150){
this.maintextdisplay=false
  }else{
    this.maintextdisplay=true
  }
},
}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0;
  padding: 0;
  border:0;
    outline:0;
  box-sizing: border-box;
  font-family: STXihei;
}
h2 {
  line-height: 50px;
}
/* 动画效果 */
.article:hover,
.mystate:hover{
  box-shadow: 0 12px 20px rgba(0, 0, 0, .1);;
    transform: translateY(-2px);
}
.rightbutton:hover,
.biao li:hover,
.touxiang:hover{
  transform: translateY(-2px);
}


.toutu {
  height: 100%;
  width: 100%;
  background-color:chartreuse;
  background-attachment: fixed;
  display: flex;
  justify-content: center;
  background: url(../assets/微信图片_20221013150708.jpg) no-repeat center center;;
  background-size:cover;
  background-attachment: fixed;
  
}
.toututext {
  position: fixed;
  top: 30%;
  color: white;
  text-shadow: 3px 3px 18px black;
  transition: all .3s linear;
}
.toututext:hover{
  transform: translateY(-2px);
}
.notoututext{
  display: none;
}
.main {
  padding-top: 10px;
  padding-bottom: 150px;
  border-radius: 13px;
  margin-top: 500px;
  margin-bottom: 200px;
  height: auto;
  width: 80%;
  background-color: white;
  position: relative;
  display: flex;
  /* justify-content: center; */
  flex-direction: column;
  align-items: center;
  box-shadow: 10px 8px 30px -9px black;
}

.touxiang {
  position: absolute;
  top: -2%;
  transition: all .1s linear;
}
.isFixed{
  position: fixed;
  top: 0;
  left: 0;
  padding: 25px 180px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 30px;
  width: 100%;
  z-index: 500;
  background-color: blue;
}
.tou {
  position: fixed;
  padding: 25px 180px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 30px;
  width: 100%;
  /* z-index: 500; */
 
}
/* .logo {
  height: 50px;
  width: 50px;
  background-color: aliceblue;
} */
.biao {
  position: relative;
  display: flex;
  justify-content: center;
  align-content: center;
  list-style: none;
}

.biao li {
  /* position: relative; */
  transition: all .3s linear;
}

.biao a {
  position: relative;
  margin: 0 15px;
  font-size: 18px;
  font-weight: bold;
  color: white;
  text-decoration: none;
  
}

.mainleftone {
  margin: 30px 40px;
  position: absolute;
  left: 10%;
  text-align: center;
  font-weight: 600;
  transition: all .2s linear;
  
}
.mainleftone:hover,
.mainlefttwo:hover{
  transform: scale(1.1);
}
.mainlefttwo {
  margin: 30px 40px;
  position: absolute;
  left: 15%;
  text-align: center;
  font-weight: 600;
  transition: all .2s linear;
}

.mainright {
  margin-top: 30px;
  display: flex;
  flex-direction: row;
  width: auto;
  height: 50px;
  position: absolute;
  right: 10%;
}

.rightbutton {
  height: 35px;
  width: 35px;
  margin: 0 7px;
  background-color: blue;
  border-radius: 20px;
  border: 0px;
  transition: all .1s linear;
}
.rightbutton i {
  color: white;
  line-height: 35px;
  text-align: center;
}
.mainmin {
  height: 100px;
  width: 150px;
  margin-top: 140px;
  text-align: center;
}

#introduce {
  margin-top: 30px;
  height: 500px;
  width: 86%;
  background-color: aliceblue;
  border-radius: 8px;
  display: flex;
  flex-direction: row;
}
.introduceleft {
  width: 50%;
  height: 480px;
  margin: 10px;
  background-color: white;
}
.introduceright {
  width: 50%;
  height: 480px;
  margin: 10px;
}
.introducerightone {
  width: 100%;
  height: 225px;
  background-color: white;
}
.introducerighttwo {
  margin-top: 15px;
  width: 100%;
  height: 237px;
  background-color: white;
}
#Ashadow {
  box-shadow: 3px 3px 7px -7px black;
}
.bigtext {
  height: auto;
  width: 100%;
  padding-left: 8%;
  margin: 20px;
}
.newarticle {
  width: 86%;
  height: auto;
  background-color: aliceblue;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
}
.article {
  height: 250px;
  width: 95%;
  background-color: white;
  margin: 20px 10px;
  display: flex;
  flex-direction: row;
  padding: 20px;
  transition: all .2s linear;
}

.mystate {
  height: auto;
  width: 95%;
  background-color: white;
  margin: 20px 10px;
  padding: 20px;
  transition: all .2s linear;
}
.articleimg {
  height: 200px;
  width: 200px;
  /* background-color: whitesmoke; */
}
.articleright {
  /* margin: 20px 0; */
  width: 70%;
  height: 200px;
  padding: 0 20px;
}
.articleintro {
  width: 100%;
  height: 60%;
  /* background-color: whitesmoke; */
  overflow: hidden;
}

.articledate {
  margin: 10px 10px;
}
.mystatetouxiang {
  padding-left: 10px;
  display: flex;
  flex-direction: row;
}
.mystatetop {
  margin-left: 20px;
}
.mystatetop p {
  margin: 10px 0;
}
.mystatecontent {
  margin: 20px 25px;
  height: auto;
  width: 80%;
  /* background-color: whitesmoke; */
  overflow: hidden;
}
.moretext{
  padding-left: 69%;
  right: 15%;
  transition: all .3s linear;
}
.moretext:hover{
  transform: translateY(-2px);
  /* text-shadow: 0px 1px 2px black; */
}
.mainbottom{
  position: absolute;
  bottom: 20px;
}
@media screen and (max-width:970px){
  .main{
    width: 97%;
  }
}
@media screen and (max-width:810px){
  h1{
    font-size: 25px;
  }
  .isFixed,
  .tou{
    flex-direction: row;
    justify-content:center;
    padding: 25px 0;
  }
  #introduce{
      width: 100%;
    }
    .newarticle{
      width: 100%;
    }
    .article{
      height: 180px;
      padding: 8px;
      margin: 10px 10px;
    }
    .articleright{
      height: 130px;
    }
  .biao {
    flex-direction: row;
    justify-content: center;
  }
  .biao a{
    margin: 35px;
  }
  .mainmin{
    margin-top: 100px;
  }
  .touxiang{
    top:-3%
  }
  .mainleftone{
font-size: 10px;

  }
  .mainlefttwo{
    font-size: 10px;
   
  }
  .mainright{
    margin-top:0px;
    right: 0px;
   position: unset;
  }
  .articleimg{
    height: 100px;
    width: 100px;
    margin-top: 20px;
  }
  .mainbottom {
 font-size:smaller;
}
}
@media screen and (max-width:570px){
  h2{
    font-size: 18px;
  }
  
  .biao a{
    margin: 16px;
  }
  .toututext {
    top: 20%;
  }
  .toututext h1{
    font-size: 20px;
  }
  .main{
    margin-top: 300px;
  }
  .mainleftone{
left: 3%;
margin: 30px 8px;
  }
  .mainlefttwo{
    left: 6%;
    margin: 30px 25px;
  }
  .articleimg{
    display: none;
  }
  .articleright {
  width: 96%;
  height: 150px;
  padding: 0 5px;
}
.mystate {
  margin: 10px 10px;
  padding: 5px;
}
.mystatecontent {
  margin: 10px 8px;
  width: 95%;
}
.mystatetop {
  margin-left: 10px;
}
.moretext{
  padding-left: 50%;
  right: 15%;
  transition: all .3s linear;
}
.mainbottom {
 font-size:xx-small;
 text-align: center;
}
}
</style>
