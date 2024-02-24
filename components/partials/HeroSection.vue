<script setup>
import { gsap } from 'gsap';

const animateElement = (element, initialState, animationProps) => {
  gsap.set(element.value, initialState);
  gsap.to(element.value, animationProps);
};

const initialStates = {
  bigText: { x: '-100%', opacity: '0' },
  profileImage: { y: '20%', opacity: '0' },
  formulaImage: { x: '-50%', opacity: '0' },
  titleText: { y: '20%', opacity: '0' },
  btns: { y: '20%', opacity: '0' },
  coins: { x: '100%', opacity: '0' },
  mouse: { opacity: '0' },
};

const animationProps = {
  duration:  1.2,
  ease: 'power4.out',
};


const bigText = ref(null);
const profileImage =  ref(null);
const formulaImage =  ref(null);
const titleText = ref(null);
const btns = ref(null);
const coins = ref(null);
const mouse = ref(null);


onMounted(() => {
    animateElement(bigText, initialStates.bigText, {
  ...animationProps,
  x: '0%',
  opacity: '1',
});

animateElement(profileImage, initialStates.profileImage, {
  ...animationProps,
  y: '0%',
  opacity: '1',
  delay:  0.6,
});

animateElement(formulaImage, initialStates.formulaImage, {
  ...animationProps,
  x: '0%',
  opacity: '1',
  duration:  1.6,
  delay:  0.6,
});

animateElement(titleText, initialStates.titleText, {
  ...animationProps,
  y: '0%',
  opacity: '1',
  duration:  1.6,
  delay:  1,
});

animateElement(btns, initialStates.btns, {
  ...animationProps,
  y: '0%',
  opacity: '1',
  duration:  1.6,
  delay:  1.2,
});

animateElement(coins, initialStates.coins, {
  ...animationProps,
  x: '0%',
  opacity: '1',
  duration:  1.6,
  delay:  1.2,
});

animateElement(mouse, initialStates.mouse, {
  ...animationProps,
  opacity: '1',
  delay:  1,
});
})

</script>

<template>
    <div class="hero-section relative flex justify-center">
        <div class="big-title-bg absolute" ref="bigText">
            <img src="@/assets/img/svg/name-bg.svg" alt="Graham Hill">
        </div>
        <picture class="graham-profile-image absolute" ref="profileImage">
            <source srcset="@/assets/img/Graham.webp" type="image/webp">
            <img src="@/assets/img/Graham.png" alt="Graham hill profile picture">
        </picture>
        <picture class="formula-image absolute" ref="formulaImage">
            <img src="@/assets/img/svg/formule.svg" alt="Formule image">
        </picture>
        <div class="container hero-container  flex justify-between items-end">
            <section class="hero-section-content">
                <div class="title">
                    <h1 ref="titleText">
                        Unikátní investiční<br/>
                        mince s motivy mistrů<br/>
                        světa <span>Formule 1.</span> 
                    </h1>
                </div>
                <div class="btns-group flex gap-8" ref="btns">
                    <SharedGlobalBtn 
                        btnType="primary-btn"
                        btnText="Zjistit více"
                        :icon="false"
                    />
                     <SharedGlobalBtn 
                        btnType="link-btn"
                        btnText="Koupit v eshopu"
                        :icon="true"
                    />
                </div>
            </section>
            <section class="hero-section-images relative" ref="coins">
                <picture class="gold-coin">
                    <source srcset="@/assets/img/hill-mince.webp" type="image/webp">
                   <img src="@/assets/img/hill-mince.png" alt="Zlatá mince">
                </picture>
                <picture class="silver-coin absolute">
                    <source srcset="@/assets/img/hill-stribro.webp" type="image/webp">
                    <img src="@/assets/img/hill-stribro.png" alt="Stříbrná mince" />
                </picture>
            </section>
        </div>

        <DesignFixedNav />
        <div class="mouse-icon absolute" ref="mouse">
            <div class="icon">
                <div class="bullet"></div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.hero-section {
    margin-bottom: 120px;

    .fixed-nav-anim {
        opacity: 0;
    }

    .graham-profile-image {
        max-width: 600px;
        top:  -300px;
        transform: translateX(80px);
        z-index: 2;
        filter: brightness(50%);
        opacity: 0;

        @media (max-width: 1300px) {
            max-width: 550px;
            top: -250px;
            transform: translateX(20px);
        }

        @media (min-width:  1536px) {
            max-width: 800px;
            top: -380px;
        }
    }

    .formula-image {
        max-width: 1520px;
        bottom: -200px;
        transform: translateX(-110px);
        z-index: 3;
        opacity: 0;

        @media (max-width: 1300px) {
            max-width: 1300px;
            bottom: -180px;
        }

        @media (min-width: 1920px) {
            bottom: -180px;
        }
    }

    .big-title-bg {
       max-width: 1200px;
       transform: translateX(-10px) translateY(20px);
       z-index: 1;
       opacity: 0;

       @media (max-width: 1300px) {
            max-width: 1120px;
            transform: translateX(-70px) translateY(20px);
       }

       @media (min-width: 1536px) {
        max-width: 1700px;
        transform: translateX(-58px) translateY(20px);
       }
    }

    .mouse-icon {
        z-index: 10;
        bottom: 0px;
        opacity: 0;
       .icon {
            position: relative;
            display: flex;
            justify-content: center;
            bottom: 0px;
            width: 18px;
            height: 30px;
            border-radius: 32px;
            border: solid 2px $color-white;
            opacity: .2;
       
       .bullet {
            width: 3px;
            height: 6px;
            position: absolute;
            background-color: $color-white;
            border-radius: 22px;
            top: 6px;
            animation: moveUpDown 2s linear infinite;
            transition: all ease .3s;

            @keyframes moveUpDown {
                0% {
                    transform: translateY(0px);
                }
                50% {
                    transform: translateY(6px);
                }
                100% {
                    transform: translateY(0px);
                }
            }
        }

       }

          &::after {
            content: '';
            position: absolute;
            width: 2px;
            height: 180px;
            top: 50px;
            background: $color-white;
            opacity: .2;
            transform: translateX(8px);
        }
    }


    .hero-container {
        display: flex;
        height: 500px;
        z-index: 5;

        @media (min-width: 1536px) {
            height: 700px;
        }
    }
    .hero-section-content {
        h1 {
            opacity: 0;
            span {
                color: $color-primary;
            }
        }

        .btns-group {
            opacity: 0;
            padding-top: 82px;
        }
    }

    .hero-section-images {
        opacity: 0;
        figure {
            margin-bottom: 0px;
        }

        .gold-coin {
            max-width: 380px;
            display: block;

                        
            @media (min-width: 1920px) {
                max-width: 540px;
            }
        }

        .silver-coin {
            max-width: 200px;
            bottom: 0px;
            left: -120px;

            @media (min-width: 1920px) {
                max-width: 265px;
            }
        }
    }
}
</style>