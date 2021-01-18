<template>
<div>
    <h1 v-if="!file">Click below to attach a file</h1>
    <form class="file_upload">
        <input
          type="file"
          accept="image/png, image/jpeg, image/jpg, image/tiff"
          class="file_input"
          @change="handleFileUploads"
        />

        <button v-if="!file" @click="attachFile" class="attachBtn" >Attach File</button>
        <div v-else class="img_container">
            <h1>Image Preview</h1>
            <img v-if="file" class="img" />
            <button class="uploadBtn">Upload</button>
        </div>
    </form>
</div>
</template>

<script>
export default {
    name: "FileUpload",
    data() {
        return {
            file: null
        }
    },
    methods: {
        attachFile(e) {
            const el = document.querySelector(".file_input");
            e.preventDefault();
            el.click();
            console.log("attaching file");
        },
        
        handleFileUploads(event) {
            event.preventDefault();
            this.file = event.target.files[0];
            console.log(event.target.files[0])
            
            let reader = new FileReader();
            reader.onload = function () {
                const image = document.querySelector(".img");
                image.src = reader.result;
            };
            reader.readAsDataURL(this.file);
        }
    }
}
</script>

<style>
    .file_input {
        visibility: hidden;
    }
    .file_upload {
        display: flex;
        width: 50vw;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 1rem;
    }
    h1 {
        font-size: 1.25rem;
        margin: 1rem;
    }
    .attachBtn, .uploadBtn {
        border: 2px solid white;
        padding: 0.5rem 2.5rem;
        color: white;
        background-color: transparent;
        font-weight: bold;
        margin: 1rem;
    }

    .attachBtn:hover, .uploadBtn:hover {
        color: black;
        background-color: white;
        transition: all 1s ease-in-out;
        translate: scale(1.1);
    }
    .img_container {
        padding: 1rem;
    }
    .img {
        margin: 0 auto;
        width: 100%;
    }
    p {
        margin: 1rem;
    }
</style>