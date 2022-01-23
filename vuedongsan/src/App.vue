<template>

  <div class="black-bg" v-if="modal==true">
  <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지의 내용</p>
      <button @click="modal=false" class="modal-btn">닫기</button>
  </div>
  </div>

  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{a}}</a>
  </div>

  <div v-for="(a,i) in products" :key="i">
    <img src='./assets/room0.jpg' class="room-img">
    <h4 @click="modal=true">{{products[i]}}</h4>
    <p>{{price[i]}}만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{신고수[i]}}</span>
  </div>
  


</template>

<script>
 
export default {
  name: 'App',
  data(){
    return{
      modal:false,
      menu:['Home','Products','About'],
      price: [10,20,30],
      products:['역삼동원룸','천호동원룸','중랑구빌라'],
      신고수:[0,0,0],
      link:['room0.jpg','room1.jpg','room2.jpg']
      
    }//뷰에서의 데이터 보관함 
  },
  methods:{
    increase(i){
      this.신고수[i]++;// vue에서는 this로 
    },
    url(i){

      
      return this.link[i];
    }


  },//함수만드는 공간
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
.black-bg{
  width:100%;height:100%;
  background: rgba(0,0,0,0,5);
  position: fixed;
  padding:20px;
}
.white-bg{
  width:100%;
  background: rgb(221, 202, 202);
  border-radius: 8px;
  padding: 20px;
}
.room-img{
  width:40%;
  margin-top:40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
.modal-btn{
  color: white;
  background: red;
  border:1px solid red;
  border-radius: 5px;
  
}
</style>
