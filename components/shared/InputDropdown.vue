<script setup>

</script>


<template>
<div class="input-dropdown flex justify-between items-center">
    <span>Vyberte si legendu</span>    
    <div class="icon">
        <img src="@/assets/img/svg/outline-arrow.svg" alt="">
    </div>
</div>
  
</template>


<style lang="scss" scoped>
.input-dropdown {
    border-radius: 32px;
    border: solid 1px $color-dark-light;
    padding: 0 16px;
    width: 276px;
    height: 48px;
    font-family: 'InterMedium';
    
    &:hover {
        cursor: pointer;
    }
    
    span {
        font-size: 14px;
        color: $color-grey;
        line-height: 18px;
        font-weight: 300;
        padding-top: 2px;
    }
}

</style>