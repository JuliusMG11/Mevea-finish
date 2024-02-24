<script setup>
import { gsap } from 'gsap';

const fixedNav = ref(null);
onMounted(() => {
    gsap.set(fixedNav.value, { opacity: '0' });
    gsap.to(fixedNav.value, {
      opacity: '1',
      duration: 1.6,
      ease: 'power4.out',
      delay: 1,
    });
})
</script>

<template>
<div class="right-fixed-navigation fixed" ref="fixedNav">
    <div class="bullet active">
        <span>Úvod</span>
    </div>
    <div class="bullet">
        <span>Sekce 2</span>
    </div>
    <div class="bullet">
        <span>Sekce 3</span>
    </div>
    <div class="bullet">
        <span>Sekce 4</span>
    </div>
    <div class="bullet">
        <span>Sekce 5</span>
    </div>
    <div class="bullet">
        <span>Sekce 6</span>
    </div>
</div>
</template>


<style lang="scss" scoped>
.right-fixed-navigation {
    display: flex;
    flex-direction: column;
    gap: 62px;
    z-index: 10;
    right: 20px;
    top: 180px;
    opacity: 0;
        

    .bullet {
        position: relative;
        width: 10px;
        height: 10px;
        border: solid 1px $color-dark-light;
        border-radius: 50%;
        background: $color-dark;

        span {
            position: absolute;
            right: 26px;
            top: -2px;
            color: $color-dark-light;
            display: block;
            opacity: 0;
            font-size: 0.75rem;
        }

        &::before {
            content: '';
            position: absolute;
            height: 80px;
            width: 1px;
            background: $color-dark-light;
            bottom: 0px;
            z-index: -1;
            left: 3.4px;
        }

        &:first-child {
            &::before {
                content: '';
                position: absolute;
                height: 0px;
                width: 0px;
                bottom: 0px;
            }
        }

        &.active {
            background: $color-primary;
            border:  none;

            span {
                opacity: 1;
            }

            &:before {
                content: '';
                position: absolute;
                z-index: 2;
                height: 30px;
                    width: 1px;
                background: $color-primary;
                top: 10px;
                left: 4.4px;
            }
        }
    }
}

</style>