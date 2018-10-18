<template>
  <b-row>
    <b-col cols="8" class="array">
      <div>
        <img class="avatar" :src="topic.topicUrl"/>
        <p class="title">{{topic.topicName}}</p>
        <span class="fan">收录了{{topic.articleCount}}篇文章 · {{topic.fans}}人关注</span>
        <div class="button">
          <button class="request">投稿</button>
          <button class="follow"> + 关注</button>
        </div>
      </div>
      <div class="navigate">
        <span class="navigate_span">最新评论</span>
        <span class="navigate_span">最新收录</span>
        <span class="navigate_span">热门</span>
      </div>
      <div class="line"></div>

      <div v-for="article in articleList" :key="article.id" class="article">
        <img class="articleThumbnail" :src="article.thumbnail"/>
        <p class="articleTitle">{{article.title}}</p>
        <p class="articleSummary">{{article.summary}}</p>
        <span class="articleSpan">{{article.nickname}}</span>
        <img src="http://p88kzenjw.bkt.clouddn.com/message.png" ><span class="articleSpan">{{article.comments}}</span>
        <img src="http://p88kzenjw.bkt.clouddn.com/like.png" ><span class="articleSpan">{{article.likes}}</span>
        <div class="line"></div>
      </div>

    </b-col>

    <b-col cols="4" class="array">
      <div>
        <p class="topicDescription">专题公告</p>
        <p class="topicIntroduce">投稿须知 :</p>
        <span class="topicIntroduce">{{topic.description}}</span>
        <p class="topicCreator">展开描述 > </p>
        <div class="line"></div>
        <p class="topicCreator">创建者</p>
        <div>
          <img class="creatorImg" :src="topic.topicUrl">
          <p class="creatorText">{{topic.creator}}</p>
        </div>
        <div class="line"></div>
        <p class="topicCreator">关注的人</p>
        <div>
          <img class="fanAvatar"v-for="fan in fansList"  :src="fan.avatar">
        </div>
      </div>
    </b-col>
  </b-row>


</template>

<script>
  export default {
    data() {
      return {
        id: this.$route.params.id,
        topic: {},
        articleList: [],
        fansList:[]
      }
    },
    activated() {
      this.id = this.$route.params.id;
      console.log(this.id);
      if (this.id == 1) {
        var t = {
          "id": 1,
          "topicName": "读书",
          "topicUrl": "https://upload.jianshu.io/collections/images/83/1.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/64/h/64",
          "summary": "读书读书读书读书读书读书读书读书",
          "articleCount": 49535,
          "fans": 1601,
          "description":"读书专题仅收录与读书有关的书评、读书笔记、阅读方法、读书清单等文章。 \n" +
          "文中不得出现非简书的链接;包括但不限于公众号、二维码、头条号、微博、一点资源等带有广告性质的信息; 配图不能带有水印。 \n" +
          "文章收录字数1000字起( 大神请忽略此限制)，请不要直接摘抄原文的话就来投稿。请注意排版美观、请不要密集投稿。 \n" +
          "投稿请查看投稿须知：https://www.jianshu.com/p/2a4cc9232f37 \n" +
          "进群请添加主编微信: MYH561...",
          "creator":"简书",
          "articleList":[
            {
              "id":1,
              "title":"小说的大纲，七个公式，人物",
              "summary":"这是我在群里的讲义内容，今天整理一下，当作文章发表。 部分图片来源于网络，如有侵权，请联系删除。 这次主要就讲小说的大纲，故事的七个公式，人物 ...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/6809532-26cc432972b30b84.png?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":2,
              "nickname":"长风镖局",
              "comments":19,
              "likes":15
            },
            {
              "id":2,
              "title":"小说的大纲，七个公式，人物",
              "summary":"这是我在群里的讲义内容，今天整理一下，当作文章发表。 部分图片来源于网络，如有侵权，请联系删除。 这次主要就讲小说的大纲，故事的七个公式，人物 ...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/6809532-26cc432972b30b84.png?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":2,
              "nickname":"长风镖局",
              "comments":19,
              "likes":15
            },
            {
              "id":3,
              "title":"小说的大纲，七个公式，人物",
              "summary":"这是我在群里的讲义内容，今天整理一下，当作文章发表。 部分图片来源于网络，如有侵权，请联系删除。 这次主要就讲小说的大纲，故事的七个公式，人物 ...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/6809532-26cc432972b30b84.png?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":2,
              "nickname":"长风镖局",
              "comments":19,
              "likes":15
            },
            {
              "id":4,
              "title":"小说的大纲，七个公式，人物",
              "summary":"这是我在群里的讲义内容，今天整理一下，当作文章发表。 部分图片来源于网络，如有侵权，请联系删除。 这次主要就讲小说的大纲，故事的七个公式，人物 ...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/6809532-26cc432972b30b84.png?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":2,
              "nickname":"长风镖局",
              "comments":19,
              "likes":15
            }
          ],
          "fansList":[
            {
              "authorId":1,
              "avatar":"http://thirdwx.qlogo.cn/mmopen/vi_32/DYAIOgq83eqZQIDSOlEmeqyS5Jn7Po3rqKGibsd6nwFCy9ZqHv38ZPWfJhFp45XKCZkydLTTjVCt7eXwYz1IaTA/132"
            },
            {
              "authorId":2,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506672/6fba7e54-24c4-4e7a-a55d-3f116a9b4653?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
            {
              "authorId":3,
              "avatar":"http://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKZWG5ibeGsJb8q8AV2NIpvCibYtP5EYL7tpYicw3BTsQN8IjKZ632axLKKWxRalIA9m0vDOsDSTHHAw/132"
            },
            {
              "authorId":4,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506650/b323ff39-4cea-4f50-9ef3-4db0661f1499?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
            {
              "authorId":5,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506624/6c24f4a5-d59f-4e3f-9e3c-ceb6819896ce?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
            {
              "authorId":6,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506667/8318d42a-c73d-4a07-8a8d-45364378bb40?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
            {
              "authorId":7,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506654/c547c1c2-1af2-48a9-a51c-8b650652f452?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
            {
              "authorId":8,
              "avatar":"https://upload.jianshu.io/users/upload_avatars/14506658/e076ee8e-5d0a-4d8c-a800-5778bb249411?imageMogr2/auto-orient/strip|imageView2/1/w/32/h/32/format/webp"
            },
          ]
        };
        this.topic = t;
        this.articleList = t.articleList;
        this.fansList = t.fansList;
      } else {
        this.topic = {};
      }
    },
    computed: function () {
      return this.topic;
    }
  }
</script>

<style scoped>
  .array{
    margin-top: 20px;
  }
  .avatar{
    width: 75px;
    height: 75px;
    border-radius: 10px;
    float: left;
  }
  .title{
    font-size: 20px ;
    font-weight: bold;
    padding-left: 100px;
  }
  .fan{
    font-size: 16px;
    color: darkgrey;
    padding-left: 25px;
  }
  .button{
    float: right;
    margin-top: -20px;
  }
  .request{
    width: 100px;
    height: 40px;
    border-radius: 30px;
    border: 1px solid limegreen;
    background-color: white;
    color: limegreen;
  }
  .follow{
    width: 100px;
    height: 40px;
    border-radius: 30px;
    border: 1px solid white;
    background-color: limegreen;
    color: white;
  }
  .line{
    border: .5px solid lightgrey;
    margin-top: 5px;
  }
  .navigate{
    margin-top: 30px;
  }
  .navigate_span{
    font-size: 16px;
    font-weight: bold;
    margin-left: 10px;
  }
  .article{
    margin-top: 20px;
  }
  .articleTitle{
    font-weight: bold;
    font-size: 20px;
  }
  .articleSummary{
    font-size: 13px;
    color: darkgrey;
  }
  .articleThumbnail{
    float: right;
    width: 150px;
    height: 100px;
  }
  .articleSpan{
    font-size: 13px;
    color: darkgrey;
  }
  .topicDescription{
    font-size: 16px;
    color: darkgrey;
  }
  .topicCreator{
    font-size: 16px;
    color: darkgrey;
    margin-top: 20px;
  }
  .topicIntroduce{
    font-size: 14px;
  }
  .creatorImg{
    float: left;
    width:30px;
    height: 30px;
    border-radius: 50%;
  }
  .creatorText{
    padding-left: 50px;
  }
  .fanAvatar{
    width: 30px;
    heigth:30px;
    border-radius: 50px;
    margin-left: -8px;
    border: 3px solid #fff;
    border-image-source: initial;
    border-image-slice: initial;
    border-image-width: initial;
    border-image-outset: initial;
    border-image-repeat: initial;
  }



</style>
