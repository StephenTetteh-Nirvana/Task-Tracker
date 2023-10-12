<template>
        <div class="div-one">
            <label>Task</label><br/>
            <input type="text" v-model="task"/>
        </div>

        <div class="div-two">
            <label>Date & Time</label><br/>
            <input type="text" v-model="date"/>
        </div>
         
        <button @click="save">Save Task</button>


           
       
 
    
       
</template>

<script>
import {ref} from 'vue'
    export default {
        name:'ShowTask',

        setup(){

            const tasks = ref([])
            const task = ref('')
            const date = ref('')

            const save = ()=>{
                if(task.value===''){
                  alert('Please add a task')
                }else if(date.value === ''){
                    alert('Please add date and time')
                }
                else{
                    const id = Math.floor(Math.random()*200);

                    const newTask = {
                        id:id,
                        task:task.value,
                        date:date.value
                    }
                    tasks.value.push(newTask)
                     
                    console.log(tasks.value)
                   task.value = '';
                   date.value = '';
                }
                 
            }

            return{
                tasks,
                task,
                date,
                save
            }
           
        }
    }
</script>

<style scoped>
.div-two{
    margin-top:10px;
}
label{
    font-size:20px;
}
input[type='text']{
    padding:10px;
    width:80%;
    border-radius:10px;
    outline:none;
    appearance: none;
}
button{
    text-align:center;
    padding:10px;
    width:40%;
    margin-top:15px;
    margin-left:25%;
    background-color:black;
    color:white;
    font-size:16px;
    font-weight:bold;
    border:none;
    border-radius:10px;
}
button:active{
    transform:scale(0.9);
}

</style>