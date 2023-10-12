<template>
    <div class="container">
        <div class="header">
            <h1>Task Tracker</h1>
            <button class="add" v-if="add" @click="showTask">Add</button>
            <button v-if="close" class="close" @click="closeTask">Close</button>

        </div>

         <div class="showTask"  v-if="show">
            <div class="div-one">
            <label>Task</label><br/>
            <input type="text" v-model="tasking"/>
             </div>

            <div class="div-two">
            <label>Date & Time</label><br/>
            <input type="text" v-model="date"/>
            </div>
         
             <button class="save" @click="save">Save Task</button>
         </div>
         
      

        <div class="hidden">
            hifdidd
        </div>
       
    </div>
    <div class="task-box" v-for="task in tasks" :key="task.id">
            <div class="inner-content">
                <div> 
                    <h1>{{ task.task }}</h1>
                    <h3>{{ task.date }}</h3>
                </div>
               
                    <div>
                        <button class="delete" @click="deleteTask(id)">Delete</button>
                    </div>
               
            </div>
        </div>
</template>

<script>
import {ref} from 'vue'

    export default {
        name:'AddTask',
        

        setup(){
               const show = ref(false)
               const add = ref(true)
               const close = ref(false)

               const showTask = () =>{
                show.value = !show.value;
                add.value = false;
                close.value = true;
               }

               const closeTask = () =>{
                show.value = !show.value;
                close.value = false;
                add.value = true;
               }

               const tasks = ref([])
            const tasking = ref('')
            const date = ref('')

            const save = ()=>{
                if(tasking.value===''){
                  alert('Please add a task')
                }else if(date.value === ''){
                    alert('Please add date and time')
                }
                else{
                    const id = Math.floor(Math.random()*200);

                    const newTask = {
                        id:id,
                        task:tasking.value,
                        date:date.value
                    }
                    tasks.value.push(newTask)
                     
                    console.log(tasks.value)
                   tasking.value = '';
                   date.value = '';
                }
                 
            }

            const deleteTask = (id)=>{
                tasks.value.splice(id, 1);
                console.log('Deleted')
                tasks.value;
            }




            return{
                   show,
                   showTask,
                   closeTask,
                   add,
                   close,
                   tasks,
                tasking,
                date,
                save,
                deleteTask,

            }
        }
    }
</script>

<style scoped>
.hidden{
    opacity:0;
    height:40px;
}
  .container{
    border:1px solid black;
    border-radius:10px;
  }
  .header{
    display:flex;
    justify-content:space-around;
  }
 .add{
    border:none;
    background-color:green;
    color:white;
    width:30%;
    height:70px;
    margin-top:10px;
    font-size:18px;
    font-weight:bold;
    border-radius:15px;
 }
 .add:active{
   transform:scale(0.9);
 }
 .close{
    border:none;
    background-color:red;
    color:white;
    width:30%;
    height:70px;
    margin-top:10px;
    font-size:18px;
    font-weight:bold;
    border-radius:15px;
 }
 .close:active{
   transform:scale(0.9);
 }
 .showTask{
    margin-top:20px;
    margin-left:30px;
 }

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
.save{
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
.save:active{
    transform:scale(0.9);
}

.task-box{
    border:1px solid black;
    border-radius:10px;
    margin-top:20px;
}
.inner-content{
    display:grid;
    grid-template-columns:2fr 1fr;
    margin-left:10px;
}
.delete{
    text-align:center;
    padding:10px;
    margin-top:15px;
    margin-left:25%;
    background-color:red;
    color:white;
    font-size:16px;
    font-weight:bold;
    border:none;
    border-radius:10px;
}
</style>