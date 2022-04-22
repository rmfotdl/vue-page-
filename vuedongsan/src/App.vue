<template>
  <div class="black-bg" v-if="모달창열렸니 === true">
    <div class="white-bg">
      <h4>상세페이지인</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false"> X </button>
    </div>
  </div>

  <div class="menu">
    <a href="" v-for="(inster,i) in menus" :key="i">{{inster}}</a>
  </div>


  <div>
    원룸샵
    <img src="./assets/room1.png" alt="" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[0] }}원룸</h4>
    <p>50만원</p>
    <button @click="신고수[0]+=1">허위매물신고</button><span>신고수 : {{신고수[0]}}</span>
  </div>
  <div>
    <img src="./assets/room2.png" alt="" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>60만원</p>
    <button @click="신고수[1]+=1">허위매물신고</button><span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room3.png" alt="" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>70만원</p>
    <button @click="신고수[2]+=1">허위매물신고</button><span>신고수 : {{신고수[2]}}</span>
  </div>
</template>

<script>
 
export default {
  name: 'App',
  data(){
    return{
      모달창열렸니 : false,
      신고수 : [0,0,0],
      menus : ['home', 'shop', 'about'],
      products : ['역삼동 원룸','천호동원룸','마포구원룸',]
    }
  },
methods : {
  increase(){
    this.신고수 += 1;
  },
},
  components: {
  
  }
}
</script>

<style>
body{
  margin:0;
}
div{
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background:darkslateblue;
  padding:15px; border-radius: 5px;
}
.menu a {
  color:white;
  padding:10px;
}
.room-img {
  width:100%;
  margin-top:40px;
}
.black-bg{
  width:100%; height:100%;
  background:rgba(0,0,0,0.5);
  position:fixed; padding:20px;
}
.white-bg{
  width:100%; background:white;
  border-radius: 8px;
  padding:20px;
  position:relative;
}
.white-bg button { 
  color:#000;
  position:absolute;
  right: 10px;
  top:10px;
  border:none;
  background:none;

}
</style>
