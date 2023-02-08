<template>
  <div class="result">
    <p>Result is {{score}} ms</p>
    <div v-if="score<250">
        <p class="great"><i class="fa-regular fa-face-surprise fa-lg"></i> Wow! You are so fast like a robot.</p>
    </div>
    <div v-else-if="score>250 && score<500">
        <p class="normal"><i class="fa-solid fa-face-smile fa-lg"></i> Your clicking skill is normal.</p>
    </div>
    <div v-else>
        <p class="slow"><i class="fa-solid fa-face-sad-tear fa-lg"></i> Oops..You are too slow like a tortoise.</p>
    </div>
  </div>
</template>

<script>
export default {
    props:["score"]
}
</script>

<style>
    .great{
        width: 400px;        
        margin: 20px auto;
        padding:150px 0; 
        font-style: italic;
        background-color: rgb(104, 154, 104); 
        border-radius: 5px;  
        color: whitesmoke;   
    }
    .normal{
        width: 400px;        
        margin: 20px auto;
        padding:150px 0; 
        font-style: italic;
        background-color: rgb(125, 161, 207); 
        border-radius: 5px;  
        color: black;  
    }
    .slow{
        width: 400px;        
        margin: 20px auto;
        padding:150px 0; 
        font-style: italic;
        background-color: rgb(156, 101, 75); 
        border-radius: 5px;  
        color: whitesmoke;  
    }
    p{
        font-style: italic;
        font-weight: bold;
    }
</style>