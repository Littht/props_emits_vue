<script setup>
const possibleSizes= ['XS','S','M','L','XL','XXL']
const props= defineProps({
    selectedSize:{required:true}
})
const emits= defineEmits({
    onChangeSize: "",
})
</script>

<template>
<div class="main">
    <h1>{{props.selectedSize}}</h1>
    <div>
        <button 
        v-for="(size,i) in possibleSizes" 
        :key=i
        :class="{'active': props.selectedSize === size}"
        @click="emits('onChangeSize', size)"
        >
        {{size}}
        </button>
    </div>
</div>
</template>
<style scoped>
    button{
        background-color: #dad8d8;
    }
    .main{
        display: flex;
        flex-direction: column;
    }
    div{
        display: flex;
        gap: 5px;
        justify-content: center;
    }
</style>