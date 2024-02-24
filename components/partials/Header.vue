<script setup>
import { gsap } from 'gsap';

const navigation =ref(null)

onMounted(() => {
     gsap.set(navigation.value, { y: '-10%', opacity: '0' });
    gsap.to(navigation.value, {
      y: '0%',
      opacity: '1',
      duration: 1.2,
      ease: 'power4.out',
    });
})
</script>


<template>
    <header class="header-section" ref="navigation">
        <div class="container relative">
            <div class="hamburger-menu fixed">
                <img src="@/assets/img/svg/menu.svg" alt="">
            </div>

            <div class="header flex justify-between">
                <section class="header-left-section flex items-center gap-8">
                    <figure class="header-logo">
                        <img src="@/assets/img/svg/logo.svg" alt="">
                    </figure>
                    <SharedInputDropdown />
                </section>
                <section class="header-right-section flex gap-8 items-center">
                    <SharedMenuPrice
                        colorSection="gold"
                        label="1 Unce zlato:"
                        price="45 572.75 Kč"
                    />
                    <SharedMenuPrice
                        colorSection="grey"
                        iconRotate="rotate"
                        label="1 Unce stříbro:"
                        price="517.83 Kč"
                    />
                    <div class="link-btn flex gap-2 items-center">
                        <div class="icon">
                            <img src="@/assets/img/svg/activity.svg" alt="">
                        </div>
                        <a href="#">
                            Vývoj cen
                        </a>
                    </div>
                </section>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>


.header-section {
    padding-top: 2rem;
    opacity: 0;

    @media (max-width: 1300px) {
        padding-right: 52px;
    }

    .header-logo {
        width: 128px;
    }

    .hamburger-menu {
       right: 20px;
        top: 60px;
    }

    .link-btn {
        a {
            text-decoration: underline;
            font-size: 0.75rem;
            color: $color-primary;
            font-family: 'InterSemibold';
        }
    }

}




</style>