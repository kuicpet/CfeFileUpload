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
    background-color: #000000;
    /* fallback for old browsers */
    background: -webkit-linear-gradient(45.34deg, #00072D 5.66%, #0A2472 50.01%, #000000 94.35%);
  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(45.34deg, #00072D 5.66%, #0A2472 50.01%, #000000 94.35%);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */ 
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}
@keyframes gradient {
	0% {
		background-position: 0% 50%;
	}
	50% {
		background-position: 100% 50%;
	}
	100% {
		background-position: 0% 50%;
	}
}
</style>
