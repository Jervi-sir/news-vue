<template>
  <div class="post">
      
    <main>
        <div class="tabs">
            <div id="edit-btn" class="tab active">
                <button v-on:click="edit">
                    Edit
                </button>
            </div>
            <div class="separator"></div>
            <div id="preview-btn" class="tab">
                <button v-on:click="preview">
                    Preview
                </button>
            </div>
        </div>
        <form id="edit" class="focus" action="#">
            <div class="image" id="image-preview">
                <label for="image">Selec cover</label>
                <input type="file" id="image" name="myfile" hidden required>
            </div>
            <div class="title">
                <input type="text" id="title"  placeholder="Title" required>
            </div>
            <div class="content">
                <textarea name="" id=""   placeholder="article" required></textarea>
            </div>
            <button type="submit" hidden>submit</button>
        </form>

        <div id="preview" >
            <div class="image">

            </div>
            <div class="title">
                <h1>Title</h1>
            </div>
            <div class="content">
                Content
            </div>
        </div>
    </main>
    <div class="actions">
        <button onclick="submit()">Submit</button>
        <button onclick="draft()">Draft</button>
    </div>
  </div>
</template>


<script>
// @ is an alias to /src

export default {
  methods: {
    edit () { 
        document.querySelector('#edit-btn').classList.add('active');
        document.querySelector('#preview-btn').classList.remove('active');
        document.querySelector('#edit').classList.add('focus');
        document.querySelector('#preview').classList.remove('focus');
    },

    preview () { 
        document.querySelector('#edit-btn').classList.remove('active');
        document.querySelector('#preview-btn').classList.add('active');
        document.querySelector('#edit').classList.remove('focus');
        document.querySelector('#preview').classList.add('focus');

        var image = document.getElementById('image');
        console.log(image);
/*
        $('#preview').find('.image').css("background-image", 'url('+  image + ')' );
        $('#preview').find('.title h1').text(title);
        $('#preview').find('.content').text(content);
        */
    },

  },
  name: 'Post',
  components: {
  }
}
</script>

<style scoped>

main {
    position: relative;
    width: 602px;
    margin: auto;
    background: #EEE7DE;
    border: 1px solid #000000;
}

main .tabs  {
    position: absolute;
    right: 0%;
    top: 0;
    display: flex;
    background-color: black;
    width: 10rem;
    justify-content: space-around;
    padding: 0.5rem 1rem;
    z-index: 2;
}

main .tabs .separator {
    border-left: 1px solid white;
}

main .tab button {
    background-color: transparent;
    color: rgb(179, 179, 179);
    border: none;
}

main .tab.active button {
    color: white;
    transform: scale(1.2);
    transition: 0.5s;
}

main .tab:hover button {
    cursor: pointer;
    color: white;
    transition: 0.5s;

}


main .image label {
    padding: 0.5rem 1rem;
    background: #796B6B;
    position: absolute;
    bottom: 0;
    right: 0;

    color: white;
}

main .image label:hover {
    cursor: pointer;
    background-color: #5e5656;
    transition: 0.5s;
}

main .image {
    position: relative;
    display: block;
    height: 20rem;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
}

main .title input {
    width: 100%;
    height: 80px;
    top: 322px;
    background: rgba(121, 107, 107, 0.19);
    border: none;
    outline: none;
    padding-left: 2rem;
}

textarea {
    resize: vertical;
    width: 100%;
    border: none;
    padding: 2rem;

}

/*-----------------------
        Preview 
        ----------------*/

main #preview .title {
    display: flex;
    align-items: center;
}
main .title h1 {
    width: 100%;
    padding: 0.5rem 2rem;
    background: rgba(121, 107, 107, 0.19);
    border: none;
    outline: none;
    padding-left: 2rem;
}

main #preview .content {
    padding: 2rem;
}


/*-------------------
        displays
        ------------*/
main #edit,
main #preview {
    display: none;
}

main #edit.focus,
main #preview.focus {
    display: block;
}
        
/*-----------------
        actions
        ------------*/
.actions {
    display: flex;
    width: 602px;
    margin: auto;
    margin-top: 1rem;
    gap: 2rem;
}

.actions button {
    background: black;
    color: white;
    padding: 0.5rem 1rem;
    border: none;
}

.actions button:nth-of-type(2) {
    background: #796B6B;

}

.actions button:hover {
    cursor: pointer;
    background: rgb(54, 54, 54);
    color: white;
    transition: 0.5s;
}

</style>

