<template>
  <!--template 안에는 html-->
  <!-- 모달창 -->
  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <div >
        <p @click="btnClose" class="btnX">X</p>
      </div>
      <div>
        <h4>상세페이지</h4>
      </div>
      <div>
        <p>상세페이지 내용</p>
      </div>
    </div>
  </div>
  <!-- 모달창 끝 -->
  
  
  <div class="menu">
    <a v-for="(a, i) in menus" :key="i">{{a}}</a>
  </div>
  <h1 :style="blueColor">VueView</h1>
  <!-- 반복문 실행 -->
  <!-- <div v-for="(a,i) in products" :key="a">
    <h4>{{ products[i] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div> -->
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 @click="btnModal">{{ products[0] }}</h4>
    <p>{{ price1 }} 만원</p>
    <!-- @ == v-on -->
    <button @click="btnReport1">허위매물신고</button> <span>신고 수 : {{ reportCount[0] }}</span>
  </div> 
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="btnModal">{{ products[1] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="btnReport2">허위매물신고</button> <span>신고 수 : {{ reportCount[1] }}</span>
  </div> 
  <div>
    <img src="./assets/room3.jpg" class="room-img">
    <h4 @click="btnModal">{{ products[2] }}</h4>
    <p>33 만원</p>
    <button @click="btnReport3">허위매물신고</button> <span>신고 수 : {{ reportCount[2] }}</span>
  </div> 
</template>

<script>
//여기는 js


export default {
  name: 'App',
  //데이터 바인딩 : JS 데이터를 HTML에 꽂아넣는 문법
  data(){ //데이터 보관함 생성
    return{ //object 형 자료로 데이터 입력
      price1 : 60,
      price2 : 70,
      blueColor : 'color:#14C38E;',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus: ['Home','Products','About'],
      reportCount: [0,0,0],
      modalStatus: false
    }
  },
  //함수만들기
  methods:{
    btnReport1(){
      this.reportCount[0]++; 
    },
    btnReport2(){
      this.reportCount[1]++; 
    },
    btnReport3(){
      this.reportCount[2]++; 
    },
    btnModal(){
      this.modalStatus=true;
    },
    btnClose(){
      this.modalStatus=false;
    }
  },
  components: {
    
  }
}
</script>

<style>
/* 여기는 css */
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}

.black-bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding:1.25rem;
}

.white-bg {
  width: 100%; background: white;
  border-radius: .5rem;
  padding: 1.25rem;
}

.white-bg span {
 margin-left: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: .1875remx;
}

.menu{
  background: #061124;
  padding: .9375rem;
  border-radius: .3125rem;
}
.menu a{
  color: white;
  padding: .625rem;
}
.room-img{
  width:80%;
  margin-top:2.5rem;
}
.btnX{
  margin-left: 26.875rem
}

</style>
