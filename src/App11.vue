<template>
  <div id="app">
      <h1>Vue transition 테스트11</h1>
      <br>
      <!-- 
          v-if else 로 동일한 요소를 나열할때는 반드시 key 속성을 다른값으로 부여 해야 한다. 
          key 를 부여 하지 않으면 vue 는 동일한 요소 하나만 만들어 놓고 내용만 update 하게 됨으로
          transition 효과가 적용 되지 않는다. 
      -->
      <transition enter-active-class="animate__animated animate__fadeIn"
                leave-active-class="animate__animated animate__fadeOut"
                mode="out-in">
        <button v-if="isOn" key="on" @click="onClicked">On</button>
        <button v-else key="off" @click="offClicked">Off</button>
      </transition>
  </div>
</template>


<script>

export default {
  name: 'App11',
  data(){
    return {
      isOn:false
    };
  },
  methods:{
    onClicked(){
        this.isOn = false;
    },
    offClicked(){
        this.isOn = true;
    }
  }
}
</script>
<style scoped>
    /* 외부 css 로딩하기 */
    @import url(https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css);
</style>
<style>

  .box{
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background-color: yellow;
  }

</style>