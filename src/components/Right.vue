<template>
     <div id="qxlp-right">
     <div id="neirong-right-top">
          <span></span>
          楼市动向-News
          <button class="leett">阅读更多</button>
        </div>
        <div id="neirong-right-lei">
          <div v-for="i in arr">
            <h4>{{i.a}}</h4>
            <h6>{{i.c}}</h6>
          </div>
        </div>
   </div>
</template>

<script>
export default {
  data() {
    return {
      arr: []
    };
  },
//   props: {
//     a: String
//   },
  created() {
    this.$http.get('http://localhost:8000/news',{id:this.$route.params.id},{emulateJSON:true}).then(e=>this.arr=e.body)
  }
};
</script>

<style>
#qxlp-right{
    margin-top: 60px;
    /* margin-right: 20px; */
    padding-bottom: 50px;
    background-color: #ccc;
}
#neirong-right-top{
    padding-top: 10px;
  overflow: hidden;
}
#neirong-right-top span{
  width: 10px;
  height: 10px;
  background-color: black;
  display: inline-block;
  margin-top: 5px;
  margin-right: 8%;
  margin-left: 10%;
}
#neirong-right-top button{
  margin-left: 8%;
}
#neirong-right-lei{
    font-size: 14px;
  text-align: center;
}
#neirong-right-lei div{
  margin-left: 8%;
  text-align: left;
  margin-top: 5%;
  position: relative;
}
#neirong-right-lei h4{
    color: #333333;
}
#neirong-right-lei h6{
    font-size: 13px;
    color: #999999;
}
.leett{
    width: 70px;
    height: 25px;
    background-color: #fff;
    border: 1px solid #000;
    font-size: 12px;
}
</style>