<script>
export default {
  methods: {
    increasement() {
      this.number++;
    },
    // clickHandler() { // E6의 단축 메서드명으로 표기
    //   alert('click!');  
    // },
    // clickHandler(event,message) {
    // console.log(event);
      // alert('event click !');
    // },
    onKeyupHandler() {
      // if (e.keyCode === 13) { //키보드 이벤트 객체에서 keyCode 속성 13은 enter키 
       console.log(' vue.js'); 
      },
    },
     // v-on 사용을 위한 이벤드 매서드 정의
    data() {  // 좌측과 동일 문법 data : function () {
      return {
        name : '철수',
        age : 19,
        message : '<h1>Hello, Vue JS! </h1>',
        message1 : 'Hello, Vue JS 1',
        className : 'red-color',
        visible : true,
        unvisible : false,
        condition : 'f',
        condition1 : true,
        fruits : ['apple', 'banna', 'orange'],
        number : 0,
      };
   },
 }

</script>

<template>
  {{ name }}
  {{ age }}
  <p>내 이름은 {{ name }} 입니다.</p>
  <p>나이는 {{ age }} 살입니다.</p>
  {{ 10 * 20 * 30 }}
  {{ name }}
  {{ message }}
  <div v-memo="[name, age]">
      <p>이름 : {{ name }}</p>
      <p>나이 : {{ age }}</p>
  </div>
  <div v-html="message"></div>
  <div v-text="message"></div>
  <div v-pre>{{  mesage1 }}</div>
  <h1 v-bind:class="className">Hello, Vue JS</h1>
  <h1 :class="className">Hello, Vue JS2</h1>
  <p v-if="visible">이 요소는 렌더링됩니다.</p>
  <p v-if="unvisible">이 요소는 렌더링되지 않습니다.</p>
  <p v-if="condition === 'A'">condition 데이터의 값은 A 입니다.</p>
  <p v-else-if="condition === 'B'">condition 데이터의 값은 B 입니다.</p>
  <p v-else> 어떤 조건에도 해당되지 않습니다.</p>
  <p v-show="condition1">v-show 디렉티브는 조건이 참입니다.</p>
  <p v-show="!condition1">v-show 디렉티브는 조건이 거짓입니다.</p>
  <h1> fruits 데이타의 반복 결과</h1>
  <ul>
    <li v-for="(fruit, index) in fruits" :key="index">
      인덱스 : {{ index }}, 값 : {{ fruit }}
    </li>
  </ul>
  <!-- <button type="botton" @click="clickHandler($evnet)">클릭</button> sdfdf --> 
  <!-- <button type="botton" @click="clickHandler($event, 'Hello')">클릭(이벤트,값)</button> -->
  <input type="text" @keyup.enter = "onKeyupHandler" />
  <h1>{{  number }}</h1>
  <h3>{{ className }}</h3>
  <button type="button" @click="increasement">증가버튼</button>
  <button @click="name= '영희'">이름 변경</button>
  <button @click="age= 100">나이 변경</button>
  
</template>

<style>
.red-color {
  color : red;
}

</style>
