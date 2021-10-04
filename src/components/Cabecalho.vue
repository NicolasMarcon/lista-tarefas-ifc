<template>
  <header>
      <h1>{{ Valor }}</h1>
  </header>
</template>

<script>
export default {
  props: ["Valor"],

};
</script>

<style>
header{
  background-color: green;
  height: 50px;
  width: 100%;
  bottom: 0px;
  margin: 0;
  text-align: center;
  padding-top:3px ;
  color: white;
  
}
</style>