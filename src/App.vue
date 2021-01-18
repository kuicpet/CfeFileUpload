<template>
  <FileUpload />
</template>

<script>
import FileUpload from "./components/FileUpload";

export default {
  name: 'App',
  components: {
    FileUpload
  }
}
</script>

<style>
* {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    outline: none;
}
body {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    line-height: 1.5;
    font-family: 'Courier New', Courier, monospace;
    color: white;
    width: 100%;
    min-height: 100vh;
    background-color: black;
}
</style>
