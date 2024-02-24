<script setup>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const headTitle = ref(null);
const boxes = ref(null);
const formule = ref(null);

const commonScrollTrigger = {
  trigger: '.boxes-section',
  start: 'top center',
  toggleActions: 'play none none none',
};

const animateElement = (element, animationProps) => {
  gsap.to(element.value, {
    scrollTrigger: commonScrollTrigger,
    ...animationProps,
  });
};


onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);
   // Head Title Animation
  animateElement(headTitle, {
    opacity:  1,
    duration:  1,
    ease: 'power4.out',
  });

  // Boxes Animation with Delay
  animateElement(boxes, {
    opacity:  1,
    duration:  1,
    delay:  1.2,
    ease: 'power4.out',
  });

  // Set initial state for formule
  gsap.set(formule.value, { x: '50%', opacity: '0' });

  // Formule Animation with Delay
  animateElement(formule, {
    opacity:  1,
    x:  0,
    duration:  1,
    delay:  1,
    ease: 'power4.out',
  });
})

</script>

<template>
  <section class="boxes-section relative">

    <div class="formule-image-bg absolute" ref="formule">
        <img src="@/assets/img/svg/formule.svg" alt="">
    </div>
    <div class="container">

        <div class="head-title" ref="headTitle">
            <h3>V současné době startujeme první etapu,</h3>
            <h2>prvních 12 mistrů světa F1</h2>
        </div>

        <div class="boxes-grid grid grid-cols-3 gap-2" ref="boxes">
            <PartialsBox
                name="Graham Hill"
                subtitle="Formula One World Champion"
                year="1962, 1968"
            >
                <source srcset="@/assets/img/hill.webp" type="image/webp">
                <img src="@/assets/img/hill.webp" alt="Graham Hill">
            </PartialsBox>
            <PartialsBox
                name="Alan Jones"
                subtitle="F1 Winner"
                year="1980"
            >
                <source srcset="@/assets/img/alan.webp" type="image/webp">
                <img src="@/assets/img/alan.png" alt="Alan Jones">
            </PartialsBox>
            <PartialsBox
                name="Nigel Mansell"
                subtitle="Formula One World Champion"
                year="1992"
            >
                <source srcset="@/assets/img/nigel.webp" type="image/webp">
                <img src="@/assets/img/nigel.png" alt="Nigel Mansell">
            </PartialsBox>
        </div>

    </div>
  </section>
</template>


<style lang="scss" scoped>
.boxes-section {
    padding-top: 220px;
    padding-bottom: 120px;
    overflow: hidden;

    .head-title {
        padding-bottom: 84px;
        text-align: center;
        opacity: 0;
        h3 {
            padding-bottom: 32px;
        }
    }

    .boxes-grid {
        opacity: 0;
    }

    .formule-image-bg {
        opacity: 0;
        right: -310px;
        bottom: -60px;
        z-index: -1;
        transform: rotate3d(0.2, 18, 1, 187deg);
    }
}
</style>