<template>
     <div class="todo">
      <div class="todos">
         <h2>{{ todo }}</h2>
            <input type="text" placeholder="Type something..." v-model="title">
            <button @click="add" >Add list</button>
            <ul>
              <li v-for="(todo, index ) in todos" :key="index" >{{ todo }} 
                 <span @click="remove(index)"  class="remove">x</span>
              </li>
            </ul>
      </div>
           
            
     </div>
</template>

<script>
export default {
     name:'ToDo',
     data(){
        return{
          todo:'Todo List App',
          title: '',
          todos:[
          'Add some list'
          ]
        }
     },
        methods:{
          add(){
            if(this.title != ''){
              // this.todos.unshift(this.title)
                 this.todos.push( this.title )
                 this.title = ""
            }
      
      },
      remove(id){
         console.log(id);
            this.todos.splice(id)
      //   this.todos.$delete(this.todos, id);
      }
    }

}
</script>

<style scoped>
     input{
       width: 150px;
       height: 50px;
       border: none;
       outline: none;
     }

     button{
         color: green;
         border: none;
         width:  80px;
         height: 30px;
         box-sizing: none;   
     } 

     .remove{
        padding: .3rem .6rem;
        background: red;
        color: #fff;
        border-radius: 30px;
     }
     .remove:hover{
        cursor: pointer;
     }

     ul li{
        padding: .4rem;
     }

      .todo{
         width: 100%;
         display: flex;
         justify-content: center;
      }
     .todos{
        width: 30%;
      

     }
</style>
        
