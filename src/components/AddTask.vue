<template>
    <div class="container">
        <div class="header">
            <h1>Task Tracker</h1>
            <button v-if="add" @click="showTask">Add</button>
            <button v-if="close" class="close" @click="closeTask">Close</button>

        </div>

        <div class="showTask" v-if="show">
            <ShowTask></ShowTask>
        </div>

        <div class="hidden">
            hifdidd
        </div>
       
    </div>
</template>

<script>
import {ref} from 'vue'
import ShowTask from '@/components/ShowTask.vue'
    export default {
        name:'AddTask',
        components:{
            ShowTask
        },

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




            return{
                   show,
                   showTask,
                   closeTask,
                   add,
                   close
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
 button{
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
 button:active{
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
</style>