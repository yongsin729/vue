<template>


  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{a}}</a>
  </div>

  <div v-for="(a,i) in products" :key="i">
    <h4>{{products[i]}}</h4>
    <p>{{price[i]}}</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{신고수[i]}}</span>
  </div>
  

</template>

<script>
 
export default {
  name: 'App',
  data(){
    return{
      menu:['Home','Products','About'],
      price: [10,20,30],
      products:['역삼동원룸','천호동원룸','중랑구빌라'],
      신고수:[0,0,0]
      
    }//뷰에서의 데이터 보관함 
  },
  methods:{
    increase(i){
      this.신고수[i]++;// vue에서는 this로 
    }


  },//함수만드는 공간
  components: {
    
  }
}
</script>

<style>
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
</style>
