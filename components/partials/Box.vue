<script setup>
const props = defineProps({
    name: {
        type: String,
        required: false,
        default: ''
    },
    subtitle: {
        type: String,
        required: false,
        default: ''
    },
    year: {
        type: String,
        required: false,
        default: ''
    }
})
</script>

<template>
<div 
    class="box"
>
    <picture class="image">
        <slot/>
    </picture>

   <div class="box-content">
        <h4>
            {{ name }}
        </h4>

        <p>
            {{ subtitle }}
        </p>

        <span>
            {{ year }}
        </span>
   </div>

   <SharedGlobalBtn 
        btnType="primary-btn"
        btnText="Investiční mince"
        :icon="false"
    />

</div>
  
</template>

<style lang="scss" scoped>
.box {
    display: flex;
    flex-direction: column;
    align-items: center;
    border: solid 1px #1D1D1D;
    padding: 32px;
    background-color: #000000;

    .image {
        width: 264px;
        display: block;
        margin-bottom: 24px;
    }

    .box-content {
        margin-bottom: 32px;
        text-align: center;
    
        h4 {
            font-size: 2rem;
            padding-bottom: 8px;
        }
        p {
            color: $color-primary;
            font-size: 1rem;
            padding-bottom: 8px;
            font-family: 'InterRegular';
        }

        span {
            display: block;
            font-size: 1rem;
            font-family: 'InterRegular';
        }
    }
}

</style>