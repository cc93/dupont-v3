<template>
  <div id="app">
    <!-- page1 -->
    <div id="page1" class="page" v-show="currentPage===1">
      <img src="../img/00_bj.jpg" alt="" class="bg">
      <!--<stars-twinkle :enable="currentPage===1" :sum="12" style="opacity: 0.9;"></stars-twinkle>-->
      <transition
        name="p1-capy"
        mode="out-in"
        v-bind:css="false"
        v-on:enter="p1CapyEnter"
        v-on:leave="p1CapyLeave"
      >
        <img v-if="p1.capy===1" key="capy1" src="../img/00_capy1.png" alt="" class="p1-capy1 pa opa">
        <img v-if="p1.capy===2" key="capy2" src="../img/00_capy2.png" alt="" class="p1-capy2 pa opa">
        <img v-if="p1.capy===3" key="capy3" src="../img/00_capy3.png" alt="" class="p1-capy3 pa opa">
        <img v-if="p1.capy===4" key="capy4" src="../img/00_capy4.png" alt="" class="p1-capy4 pa opa">
      </transition>
      <transition
        name="p1-door"
        mode="out-in"
        v-bind:css="false"
        v-on:enter="p1DoorEnter"
        v-on:leave="p1DoorLeave"
      >
        <img v-show="p1.door" key="door" src="../img/00_door.png" alt="" class="p1-door pa opa">
      </transition>
      <div class="prompt p1-prompt pa"
           v-show="p1.prompt"
           @click="onClickPrompt"
      >
        <div class="prompt-1 pa"></div>
        <div class="prompt-2 pa"></div>
      </div>
    </div>
    <!-- /page1 -->
    <!-- page2 -->
    <div id="page2" class="page" v-show="currentPage===2">
      <img src="../img/bj01.jpg" alt="" class="bg">
      <img src="../img/01_lamp.png" alt="" class="p2-lamp pa">
      <transition
        name="p2-capy"
        v-bind:css="false"
        v-on:enter="p2CapyEnter"
        v-on:leave="p2CapyLeave"
      >
        <img v-show="p2.capy===1" src="../img/01_capy01.png" alt="" class="p2-capy1 pa">
      </transition>
      <div class="prompt p2-prompt pa"
           v-show="p2.prompt"
           @click="onClickPrompt"
      >
        <div class="prompt-1 pa"></div>
        <div class="prompt-2 pa"></div>
      </div>
    </div>
    <!-- /page2 -->
    <!-- page3 -->
    <div id="page3" class="page" v-show="currentPage===3">
      <img src="../img/bj05.png" alt="" class="bg">
      <transition
        name="p3-capy"
        mode="out-in"
        v-bind:css="false"
        v-on:enter="p3CapyEnter"
        v-on:leave="p3CapyLeave"
      >
        <div class="slogan-box pa opa" v-if="p3.capy===1" key="capy1" @click="clickSlogan">
          <img src="../img/02_capy01.png" alt="" class="p3-capy1 pa">
        </div>
        <img v-if="p3.capy===2" key="capy2" src="../img/02_capy03.png" alt="" class="p3-capy3 pa opa">
      </transition>
      <div class="prompt p3-prompt pa"
           v-show="p3.prompt"
           @click="onClickPrompt"
      >
        <div class="prompt-1 pa" style="background: #fc3030"></div>
        <div class="prompt-2 pa" style="background: #fc3030"></div>
      </div>
    </div>
    <!-- /page3 -->
    <!--page4-->
    <div id="page4" class="page" v-show="currentPage===4">
      <img src="../img/bj05.png" alt="" class="bg">
      <transition
        name="p4-sofa"
        v-bind:css="false"
        v-on:enter="p4SofaEnter"
      >
        <img v-if="p4.capy>=1" key="capy1" src="../img/sofa.png" alt="" class="sofa pa">
      </transition>
      <transition
        name="p4-capy"
        mode="out-in"
        v-bind:css="false"
        v-on:enter="p4CapyEnter"
        v-on:leave="p4CapyLeave"
      >
        <div class="slogan-box pa opa" v-if="p4.capy===2" key="capy2" @click="clickSlogan">
          <img src="../img/03_capy01.png" alt="" class="p3-capy1 pa">
        </div>
        <img v-if="p4.capy===3" key="capy3" src="../img/03_capy02.png" alt="" class="p4-capy2 pa opa">
      </transition>
      <div class="prompt p4-prompt pa"
           v-show="p4.prompt"
           @click="onClickPrompt"
      >
        <div class="prompt-1 pa" style="background: #fc3030"></div>
        <div class="prompt-2 pa" style="background: #fc3030"></div>
      </div>
    </div>
    <!--/page4-->
    <!-- page5 -->
    <div id="page5" class="page" v-show="currentPage===5">
      <img src="../img/bj05.png" alt="" class="bg">
      <img src="../img/sofa.png" alt="" class="sofa pa">
      <transition
        name="p5-curtain"
        v-bind:css="false"
        v-on:enter="p5CurtainEnter"
      >
        <img v-if="p5.capy>=1" src="../img/curtain.png" alt="" class="p5-curtain pa">
      </transition>
      <transition
        name="p5-curtain01"
        v-bind:css="false"
        v-on:enter="p5CurtainEnter"
      >
        <img v-if="p5.capy>=2" src="../img/curtain01.png" alt="" class="p5-curtain01 pa opa">
      </transition>
      <transition
        name="p5-draw"
        v-bind:css="false"
        v-on:enter="p5CurtainEnter"
      >
        <img v-if="p5.capy>=3" src="../img/draw.png" alt="" class="p5-draw pa">
      </transition>
      <transition
        name="p5-table"
        v-bind:css="false"
        v-on:enter="p5CurtainEnter"
      >
        <img v-if="p5.capy>=4" src="../img/table.png" alt="" class="p5-table pa">
      </transition>
      <transition
        name="p5-capy"
        mode="out-in"
        v-bind:css="false"
        v-on:enter="p5CapyEnter"
        v-on:leave="p5CapyLeave"
      >
        <div class="slogan-box pa opa" v-if="p5.capy===5" key="capy5" @click="clickSlogan">
          <img src="../img/04_capy01.png" alt="" class="p3-capy1 pa">
        </div>
        <img v-if="p5.capy===6" key="capy5" src="../img/04_capy02.png" alt="" class="p4-capy2 pa opa">
      </transition>
      <div class="prompt p5-prompt pa"
           v-show="p5.prompt"
           @click="onClickPrompt"
      >``
        <div class="prompt-1 pa" style="background: #fc3030"></div>
        <div class="prompt-2 pa" style="background: #fc3030"></div>
      </div>
    </div>
    <!-- /page5 -->
    <!-- /age6 -->
    <div id="page6" class="page" v-show="currentPage===6">
      <img src="../img/08_bj.jpg" alt="" class="bg">
      <img src="../img/08_logo.png" alt="" class="p6-logo pa">
      <transition
        name="p6-photo"
        v-bind:css="false"
        v-on:enter="p6PhotoEnter"
      >
        <img v-if="p6.capy>=1" src="../img/08_photo.png" alt="" class="p6-photo pa">
      </transition>
    </div>
    <!-- /page6 -->
  </div>
</template>

<script>
  import Velocity from '../js/velocity'
  import StarsTwinkle from './components/StarsTwinkle.vue'

  export default {
    name: 'app',
    components: {StarsTwinkle},
    data () {
      return {
        currentPage: 0,
        p1: {capy: 0, prompt: false, door: false},
        p2: {capy: 0, prompt: false},
        p3: {capy: 0, prompt: false},
        p4: {capy: 0, prompt: false},
        p5: {capy: 0, prompt: false},
        p6: {capy: 0, prompt: false}
      }
    },
    watch: {
      'currentPage': function (currentPage) {
        //触发字幕动画
        this['p' + currentPage]['capy'] = 1;
      }
    },
    mounted(){
      this.currentPage = 1;
    },
    methods: {
      onClickPrompt(e){
        this.currentPage++;
      },
      p1CapyEnter: function (el, done) {
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        Velocity(el, {opacity: 1, translateY: '0'}, 500);
        let duration = 500;
        if (this.p1.capy === 4) {
          duration = 1200;
        }
        Velocity(el, {opacity: 1}, duration, () => {
          this.p1.capy++;
          if (this.p1.capy === 3) {
            this.p1.door = true;
          }
          done();
        });
      },


      p1CapyLeave: function (el, done) {
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, done);
      },
      p1DoorEnter: function (el, done) {
        Velocity(el, {opacity: 0, translateY: '-30px', scale: 0.7, transformOrigin: '0 0'}, 0);
        Velocity(el, {opacity: 1, translateY: '0', scale: 1}, {
          delay: 500,
          duration: 1200,
          easing: [.22, .81, .58, .96],
          complete: () => {
            this.p1.prompt = true;
            done();
          }
        });
      },
      p1DoorLeave: function (el, done) {
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, done);
      },
      p2CapyEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        Velocity(el, {opacity: 1, translateY: '0'}, 500);
        Velocity(el, {opacity: 1}, 500, () => {
          this.p2.capy++;
          done();
        });
      },
      p2CapyLeave(el, done){
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, () => {
          this.p2.prompt = true;
          done();
        });
      },
      p3CapyEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        let delay = 0;
        if (this.p3.capy === 2) {
          delay = 300;
        }
        Velocity(el, {opacity: 1, translateY: '0'}, {duration: 500, delay: delay});
        let duration = 500;
        if (this.p3.capy === 1) {
          duration = 1200;
        }
        Velocity(el, {opacity: 1}, duration, () => {
          if (this.p3.capy !== 1) {
            this.p3.capy++;
          }
          done();
        });
      },
      p3CapyLeave(el, done){
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, () => {
          if (this.p3.capy === 3) {
            this.p3.prompt = true;
          }
          done();
        });
      },
      clickSlogan(){
        this['p' + this.currentPage]['capy']++;
      },


      p4CapyEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        let delay = 0;
        if (this.p4.capy === 3) {
//                    duration = 1200;
          delay = 300;
        }
        Velocity(el, {opacity: 1, translateY: '0'}, {duration: 500, delay: delay});
        let duration = 500;
        if (this.p4.capy === 2) {
//                    duration = 1200;
          duration = 0;
        }
        Velocity(el, {opacity: 1}, duration, () => {
          if (this.p4.capy !== 2) {
            this.p4.capy++;
          }
          done();
        });
      },
      p4CapyLeave(el, done){
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, () => {
          if (this.p4.capy === 4) {
            this.p4.prompt = true;
          }
          done();
        });
      },
      p4SofaEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        Velocity(el, {opacity: 1, translateY: '0'}, {duration: 500});
        Velocity(el, {opacity: 1}, 500, () => {
          this.p4.capy++;
          done();
        });
      },
      p5CurtainEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        Velocity(el, {opacity: 1, translateY: '0'}, {duration: 400});
        Velocity(el, {opacity: 1}, 100, () => {
          this.p5.capy++;
          done();
        });
      },


      p5CapyEnter(el, done){
        Velocity(el, {opacity: 0, translateY: '30px'}, 0);
        let delay = 0;
        if (this.p5.capy === 6) {
          delay = 300;
        }
        Velocity(el, {opacity: 1, translateY: '0'}, {duration: 500, delay: delay});
        let duration = 500;
        if (this.p5.capy === 5) {
//                    duration = 1200;
          duration = 0;
        }
        Velocity(el, {opacity: 1}, duration, () => {
          if (this.p5.capy !== 5) {
            this.p5.capy++;
          }
          done();
        });
      },
      p5CapyLeave(el, done){
        Velocity(el, {opacity: 0, translateY: '-30px'}, 500, () => {
          if (this.p5.capy === 7) {
            this.p5.prompt = true;
          }
          done();
        });
      },
      p6PhotoEnter(el, done){
        let duration = 900;
        //initial state
        Velocity(el, {left: 0, top: 0, scale: 3.05, rotateZ: 4}, 0);
        Velocity(el, {left: 0, top: 0, scale: 2.5, rotateZ: 4}, {
          duration: 200, complete: () => {
            //end state
            Velocity(el, {left: 56, scale: 1}, {duration: duration, easing: 'linear', queue: false});
            Velocity(el, {top: 273, rotateZ: 0}, {
              duration: duration,
              easing: [1, 0, .5, 1.99],
              queue: false,
              complete: done
            });
          }
        });
      }
    }
  }
</script>

<style src="../css/base.css"></style>
<style>
  #app {
    width: 100%;
    height: 100%;
    position: relative;
  }

  .page {
  }

  .bg {
    /*left: 0;*/
    /*top: 0;*/
    /*position: absolute;*/
  }

  .p1-capy1 {
    left: 455px;
    bottom: 70px;

  }

  .p1-capy2 {
    left: 315px;
    bottom: 70px;

  }

  .p1-capy3 {
    left: 274px;
    bottom: 70px;
  }

  .p1-capy4 {
    left: 212px;
    bottom: 70px;
  }

  .p1-door {
    left: 768px;
    top: 115px;
  }

  .prompt {
    width: 80px;
    height: 80px;
  }

  .prompt-1 {
    width: 20px;
    height: 20px;
    left: 50%;
    top: 50%;
    -webkit-transform: translateX(-50%) translateY(-50%);
    -moz-transform: translateX(-50%) translateY(-50%);
    -ms-transform: translateX(-50%) translateY(-50%);
    -o-transform: translateX(-50%) translateY(-50%);
    transform: translateX(-50%) translateY(-50%);
    border-radius: 50%;
    background: #cccdd0;
    opacity: 0.9;
  }

  .prompt-2 {
    width: 20px;
    height: 20px;
    left: 50%;
    top: 50%;
    -webkit-transform: translateX(-50%) translateY(-50%);
    -moz-transform: translateX(-50%) translateY(-50%);
    -ms-transform: translateX(-50%) translateY(-50%);
    -o-transform: translateX(-50%) translateY(-50%);
    transform: translateX(-50%) translateY(-50%);
    border-radius: 50%;
    background: #cccdd0;
    -webkit-animation: promptInflate 1.2s linear infinite;
    animation: promptInflate 1.2s linear infinite;
  }

  @-webkit-keyframes promptInflate {
    0% {
      width: 20px;
      height: 20px;
      opacity: 0.9;
    }
    75% {
      width: 60px;
      height: 60px;
      opacity: 0.1;
    }
    100% {
      opacity: 0;
    }
  }

  @keyframes promptInflate {
    0% {
      width: 20px;
      height: 20px;
      opacity: 0.9;
    }
    75% {
      width: 60px;
      height: 60px;
      opacity: 0.1;
    }
    100% {
      opacity: 0;

    }
  }

  .p1-prompt {
    left: 919px;
    top: 315px;
  }

  .p2-lamp {
    left: 648px;
    top: 36px;
  }

  .p2-capy1 {
    left: 440px;
    bottom: 70px;
  }

  .p2-prompt {
    left: 644px;
    top: 100px;
  }

  .slogan-box {
    width: 100%;
    height: 86px;
    left: 0;
    bottom: 42px;
    background: url(../img/02_capy02.png) 0 0 no-repeat;
  }

  .p3-capy1 {
    left: 50%;
    top: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }

  .p3-capy3 {
    left: 440px;
    bottom: 70px;
  }

  .p3-prompt {
    left: 428px;
    top: 437px;
  }

  .sofa {
    left: 160px;
    bottom: 75px;
  }

  .p4-capy2 {
    left: 368px;
    bottom: 70px;
  }

  .p4-prompt {
    right: 123px;
    bottom: 306px;
  }

  .p5-curtain {
    right: 56px;
    bottom: 105px;
  }

  .p5-curtain01 {
    left: 540px;
    bottom: 344px;
  }

  .p5-draw {
    left: 282px;
    top: 81px;
  }

  .p5-table {
    left: 186px;
    bottom: 23px;
  }

  .p5-prompt {
    right: 461px;
    bottom: 220px;
  }

  .p6-logo {
    left: 100px;
    top: 100px;
  }

  .p6-photo {
    left: 66px;
    top: 172px;
  }
</style>
