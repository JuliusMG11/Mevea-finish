<script setup>
const props = defineProps({
    colorSection: {
        type: String,
        required: false,
        default: ''
    },
    iconRotate: {
        type: String,
        required: false,
        default: ''
    },
    label: {
        type: String,
        required: false,
        default: ''
    },
    price: {
        type: String,
        required: false,
        default: ''
    }
})
</script>

<template>
    <div class="menu-price flex" :class="colorSection">
        <div class="icon" :class="iconRotate">
            <svg xmlns="http://www.w3.org/2000/svg" width="11.222" height="11.222" viewBox="0 0 11.222 11.222">
                <path id="Path_16" data-name="Path 16" d="M7.056,7.936,7.935,0,0,.88Z" transform="translate(0 5.61) rotate(-45)" fill="#ffffff"/>
            </svg>
        </div>
        <div class="content-section">
            <span>{{ label }}</span>
            <p>{{ price }}</p>
        </div>
    </div>

</template>

<style lang="scss" scoped>
.menu-price {
    gap: 8px;

    &.gold {
        svg {
            path {
                fill: $color-primary;
            }
        }

        span {
            color: $color-primary;
        }
    }

    &.grey {
        svg {
            path {
                fill: $color-light-grey;
            }
        }

        span {
            color: $color-light-grey;
        }
    }


    .icon {
        svg {
            position: relative;
            top: 4px;
        }
        &.rotate {
            svg {
                transform: rotate(180deg);
                top: 0px;
            }
        }
    }

    span {
        font-size: 0.75rem;
        font-weight: 300;
        font-family: 'InterSemibold';
        display: block;
    }

    p {
        font-size: 0.75rem;
        font-family: 'InterSemibold';
        color: $color-white;
    }
}
</style>