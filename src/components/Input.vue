<template>
  <label>
    <input placeholder=" " @input="changeFn">
    <span>{{placeholder}}</span>
  </label>
</template>

<script>
  export default {
    props: ['placeholder', 'changeFn'],
    methods: {
      changeFallback() {
        console.log("uhaeuea")
      }
    }
  }
</script>

<style scoped>

label {
  margin:20px 0;
  position:relative;
  display:inline-block;
  width: 100%;
}

span {
  padding:10px;
  pointer-events: none;
  position:absolute;
  left:0;
  top:0;
  transition: 0.2s;
  transition-timing-function: ease;
  transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
  opacity:0.5;
}

input {
  padding:10px;
  width: 100%;
}

input:focus + span, input:not(:placeholder-shown) + span {
  opacity:1;
  transform: scale(0.75) translateY(-100%) translateX(-30px);
}

/* For IE Browsers*/
input:focus + span, input:not(:-ms-input-placeholder) + span {
  opacity:1;
transform: scale(0.75) translateY(-100%) translateX(-30px);
}

</style>
