<script setup lang="ts">
import { onMounted, ref} from 'vue';


const fadeInCss = ref();
const fadeOutCss = ref();

onMounted(()=>{

  // console.log('test')
  let elementsArray = document.querySelectorAll(".pic");
  
  // console.log(elementsArray);
  window.addEventListener('scroll', fadeIn ); 
  function fadeIn() {

      for (let i = 0; i < elementsArray.length; i++) {
          const elem = elementsArray[i]
          
          console.log(`ele: ${i}  ${elem.getBoundingClientRect().top} window: ${window.innerHeight}` )
          
          const distInView = elem.getBoundingClientRect().top - window.innerHeight + 20;
          if (distInView < 0) {
              elem.classList.add("inView");
          } else {
              elem.classList.remove("inView");
          }
          const is_trans = elem.classList.contains('trans');
          if(is_trans){
            if(elem.getBoundingClientRect().top - window.innerHeight<= 20 ){
              console.log('test');  
              fadeOutCss.value={
                
              }
              fadeInCss.value = {
                'animation': 'appear_from_bottom ease '+1.5+'s',
                'opacity': 1
              }
            }

          }
      }
  }

})



</script>
<template>
  <div class="container">
    <h2 class="contents">선우와 수민이 모바일 청첩장 만들기 우당탕탕 대작전</h2>
    


      <div class="album">
  
        <img class="pic scroll rotation bottom-right" src="@/assets/images/soomin_01.jpeg" />
        <img class="pic scroll rotation bottom-right" src="@/assets/images/soomin_01.jpeg" />
        

        
        <img v-on:scroll="" class="pic scroll rotation bottom-right" src="@/assets/images/soomin_01.jpeg" />
        <img class="pic scroll rotation bottom-right" src="@/assets/images/soomin_01.jpeg" />

      
      </div>
      <div class="album">

<!--         
        <img class="pic scroll trans soomin" src="@/assets/images/soomin_01.jpeg" :style="fadeInCss"/>
        <img class="pic scroll trans soomin" src="@/assets/images/soomin_01.jpeg" :style="fadeInCss"/> -->

        <img class="pic scroll trans sunwoo" src="@/assets/images/sunwoo_01.jpeg" :style="fadeInCss"/>
        <img class="pic scroll trans sunwoo" src="@/assets/images/sunwoo_01.jpeg" :style="fadeInCss"/>

      </div>
      
    </div>
  <!-- <img class="sunwoo 01" src="@/assets/images/sunwoo_01.jpeg" /> -->
</template>
<style>
/* 애니메이션 */
@keyframes appear{
  from {
    opacity: 0;
  }

  to{
    opacity: 1;
  }
}
@keyframes appear_from_bottom{
  0%{
    transform: translateX(150px);
    opacity: 0;
  }

  100%{
    opacity: 1;
  }
}

.pic {
  width:300px;
  height:auto;
}

.rotation {

  -webkit-transform: translateY(50px) rotate(-5deg) translateZ(0);
  transform: translateY(50px) rotate(-5deg) translateZ(0);

}
.scroll{
  -webkit-transition-delay: .3s;
  -o-transition-delay: .3s;
  transition-delay: .3s;
  -webkit-transition: .4s;
  -o-transition: .4s;
  transition: .4s;
  opacity: 0;
}
.bottom-right.inView {
    opacity: 1;
    -webkit-transform: translateY(0px) rotate(0deg) translateZ(0);
    transform: translateY(0px) rotate(0deg) translateZ(0);
}
.inView {
    opacity: 1;
    -webkit-transform: translateY(0px) rotate(0deg) translateZ(0);
    transform: translateY(0px) rotate(0deg) translateZ(0);
}
.sunwoo{
  /* width: 305px; */
  opacity: 0;

}
.soomin{
  

  opacity: 1;
}

</style>
