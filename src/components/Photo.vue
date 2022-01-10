<template>
<div>

    <div > 
        <img class="main-img" :src=data.img alt="사진" />
        {{data.content}}
    </div>

    {{data}}
</div>
    
</template>

<script>
export default {
  name: 'Photo',
  props: ['data'],
  data() {
    return {
       
    }
  },
  methods: {
 
 },
}


</script>

<style scoped>
    .main-img {
        width : 500px;
        margin : 0px 100px 0px 100px;
    }

</style>

