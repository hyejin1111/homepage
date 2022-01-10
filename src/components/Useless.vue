<template>
<div>

<textarea class="textbox" ref="textbox1" v-model="inputtext" />

<button v-on:click="hide"> 사라져라 얍 </button>

</div>
    
</template>

<script>
export default {
  name: 'Useless',
  mounted() {
    console.log(this.$refs.textbox1)
  },
  props: {
  },
  data() {
    return {
      inputtext : '',
    }
  },
  methods: {
    hide : function() {
      this.$refs.textbox1.style.display = "none";
    }
 },
}


</script>

<style scoped>

.textbox {
    height: 450px;
    width: 600px;
    margin: 5px;
    display: block;
}

</style>

