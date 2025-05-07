

<template>
   <div class="item">
    <p> {{ book.title }}</p>
   </div>
   <Button label="Submit" />
</template>

<script setup>


export default {
    props: ['book'],
    
}

</script>



<style>
.item{
    
    max-width: 500px;
    text-align: center;
}
</style>