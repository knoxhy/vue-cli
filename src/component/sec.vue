<template>
  <div id="secondcomponent">
    <h1>I am another page</h1>
    <a> written by {{ author }} </a>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <h1 style="line-height: 36px; color: #20A0FF">豆瓣电影排行榜</h1>
      </div>
      <div v-for="article in articles" class="text item">
        {{article.title}}
      </div>
    </el-card>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      author: "微信公众号 love u",
      articles: [],
    }
  },
   mounted() {
    this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10', {}, {
        headers: {
        },
        emulateJSON: true
    }).then(suc=> {
      // 这里是处理正确的回调
        this.articles = suc.data.subjects
        // this.articles = response.data["subjects"] 也可以
    }, err=> {
        // 这里是处理错误的回调
        console.log(err)
    });
  }
}

</script>

<style>
.text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }

  .box-card {
    width: 480px;
  }
</style>