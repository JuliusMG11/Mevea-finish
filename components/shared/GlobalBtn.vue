<script setup>
const props = defineProps({
    btnType: {
        type: String,
        required: false,
        default: ''
    },
    btnText: {
        type: String,
        required: false,
        default: ''
    },
    icon: {
        type: Boolean,
        required: false,
        default: false
    }
})
</script>


<template>
  <button class="button flex" :class="btnType">
    <div class="icon" v-if="icon">
        <img src="@/assets/img/svg/buy.svg" alt="">
    </div>
    {{ btnText }}
  </button>
</template>

<style lang="scss" scoped>

.button {
    justify-content: center;
    align-items: center;
     font-size: 0.875rem;
     font-family: 'InterMedium';
     transition: all ease .3s;

    &.link-btn {
        background: none;
        border: none;
        gap: 12px;
        color: $color-primary;
    }

    &.primary-btn {
        background: linear-gradient(139deg, #B87C1D, #EAC666, #EAC666);
        border: none;
        width: 160px;
        height: 48px;
        border-radius: 32px;
        color: $color-dark;

        &:hover {
            background: $color-primary;
            transition: all ease .3s;
        }
    }
}


</style>