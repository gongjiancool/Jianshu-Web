<template>
  <div>
    <div  v-for="all in topicList"  class="top">
      <p class="title">简书推荐专题</p>
      <div class="div">
        <img class="all-img" :src="all.url">
        <button class="button">+ 关注</button>
        <div class="down">
          <a>{{all.text}}</a><br>
          <a class="introduce-p">{{all.introduce}}</a><br>
          <a class="introduce-p">{{all.num1}}篇文章 - {{all.num2}}人关注</a>
        </div>
      </div>
      <div class="line"></div>



    </div>
  </div>
</template>

<script>
    export default {
        name: "title",
      data() {
        return {
          topicList: [
            {
              "id": 1,
              "url":"https://upload.jianshu.io/collections/images/4/sy_20091020135145113016.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/144/h/144/format/webp",
              "text" : "简书电影",
              "introduce":"故事专题，不论是旅行生活中亲身经历的真实故事，还是童话玄幻遐想的...",
              "num1":"111",
              "num2":"344",
            },
            {
              "id": 2,
              "url": "https://upload.jianshu.io/collections/images/14/6249340_194140034135_2.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/144/h/144/format/webp",
              "text" : "摄影",
              "introduce":"故事专题，不论是旅行生活中亲身经历的真实故事，还是童话玄幻遐想的...",
              "num1":"111",
              "num2":"344",

            },
            {
              "id": 3,
              "url": "https://upload.jianshu.io/collections/images/21/20120316041115481.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/144/h/144/format/webp",
              "text" :"手绘",
              "introduce":"故事专题，不论是旅行生活中亲身经历的真实故事，还是童话玄幻遐想的...",
              "num1":"111",
              "num2":"344",
            },
            {
              "id": 4,
              "url": "https://upload.jianshu.io/collections/images/76/12.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/144/h/144/format/webp",
              "text" : "格列柯南",
              "introduce":"故事专题，不论是旅行生活中亲身经历的真实故事，还是童话玄幻遐想的...",
              "num1":"111",
              "num2":"344",
            },
            {
              "id": 5,
              "url": "https://upload.jianshu.io/collections/images/13/%E5%95%8A.png?imageMogr2/auto-orient/strip|imageView2/1/w/144/h/144/format/webp",
              "text":"自然科普",
              "introduce":"故事专题，不论是旅行生活中亲身经历的真实故事，还是童话玄幻遐想的...",
              "num1":"111",
              "num2":"344",
            }
          ]
        }
      }
    }
</script>

<style scoped>
  button{
    width: 100px;
    height: 40px;
    border-radius: 30px;
    border: 1px solid white;
    background-color: limegreen;
    color: white;
  }
  .line{
    border: .5px solid lightgrey;
    margin-top: 10px;
  }
  .introduce-p{
    font-size: 13px;
    color: darkgrey
  }
  .title{
    color:red;
    font-size: 13px
  }
  .top{
    margin-top: 10px
  }
  .all-img{
    width: 60px;
    height: 60px;
    float: left;
  }
  .button{
    float: right;
  }
  .down{
    padding-left: 80px
  }
  .div{
    margin-top: 5px;
  }
</style>
