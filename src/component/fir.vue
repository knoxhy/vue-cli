<template>
  <div id="firstcomponent">
    <h1>I am a title.</h1>
    <a> written by {{ author }} </a>
    <el-row>
	  <el-col :span="8" v-for="(o, index) in 3" :offset="index > 0 ? 1 : 0">
	    <el-card :body-style="{ padding: '0px' }">
	      <img src="../assets/ch.png" class="image">
	      <div style="padding: 14px;">
	        <span>好吃的汉堡</span>
	        <div class="bottom clearfix">
	          <time class="time">{{ currentDate }}</time>
	          <el-button type="text" class="button">操作按钮</el-button>
	        </div>
	      </div>
	    </el-card>
	  </el-col>
	</el-row>
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
    	currentDate: new Date(),
      author: "lalala 0 hy"
    }
  }
}
</script>

<style>
.time {
    font-size: 13px;
    color: #999;
  }
  
  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .button {
    padding: 0;
    float: right;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  
  .clearfix:after {
      clear: both
  }
</style>