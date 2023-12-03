<template>
<div>
    <div>
    <input type="text" name="" id="input">
    <button @click="addLi" class="add">
        Add
    </button>
    </div>
    <div>
    <ul id="ul">

    </ul>
    </div>
</div>
</template>
<script>
export default{
    data(){
        return{
        text:''
        }
    },
    methods: {
    addLi(){
        let ul = document.getElementById('ul')
        this.text = document.getElementById('input').value.trim()
        if(this.text !== ''){
        let li = document.createElement('li')
        let p = document.createElement('p')
        let button =document.createElement('button')
        button.textContent = 'Remove'
        button.addEventListener('click',function(){
            li.remove()
        })
    let inp = document.createElement('input')
    inp.setAttribute("type" , "checkbox")
        button.classList.add('remove')
        p.textContent = this.text
        li.appendChild(p)
        li.appendChild(button)
        ul.appendChild(li)
        document.getElementById('input').value = ''
    }
    else{
        alert('Firstly fill')
        document.getElementById('input').value = ''

        
    }
    }
    }
}
</script>

<style>
body{
    text-align: center;
}
input{
    width: 80%;
    padding: 10px;
    border-radius: 10px 0 0 10px;
    border:1px solid black;
}
#app{
    padding: 100px;
}
ul{
    
    text-align: center;
}
li{
    list-style: none;
    display: flex;
    margin: 0 auto;
    border: 1px solid black;
    padding: 10px;
    border-radius: 20px;
    justify-content: space-between;
    height: fit-content;
    align-items: center;
    margin-bottom: 20px;
}
.remove{
   width: fit-content;
   height: fit-content;
    border:1px solid red;
    padding: 5px 10px;
    background-color: red;
    border-radius: 20px;
    color:white
}
.add{
    padding: 10px 20px ;
    background-color: green;
    border: 1px solid green;
    border-radius: 0 10px 10px 0;
    color: white;
}
</style>