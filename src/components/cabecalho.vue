<template>
  <h2>
    {{titulo}}
  </h2>
</template>

<script>
export default {
    props: ["titulo"]
}
</script>

<style>
h2 {
    margin: 0;
    padding: 10px;
    text-align: center;
    background-color:cadetblue;
}

</style>