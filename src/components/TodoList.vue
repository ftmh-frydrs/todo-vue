<template>
  <div class="flex items-center justify-center">
    <input v-model="list" class="rounded border mx-2 px-3 py-2" type="text">
  <button @click="add" class="bg-blue-400 px-5 py-2 rounded text-white">ADD</button>
  </div>
  <ul>
    <li class="bg-blue-300 w-[300px] px-3 py-2 mt-5 rounded mx-auto flex" v-for="(list , index) in lists" :key="index">
        {{list.text}}
       <div class="flex mx-auto mr-1">
        <button class="mx-1" @click="remove()">❌</button>
        <button class="mx-1" @click="edit(index)">🖍️</button>
       </div>
    </li>
    
  </ul>
</template>

<script>
export default {
    data(){
        return{
            editTask:null,
              list:'',
              lists : [
              
              ],
        };
    },
    methods : {
        add(){
            if(this.lists.length === '') return ;
            
            if(this.editTask === null){
                this.lists.push({
                    id : Math.random(),
                    text :this.list
                })
            }else{
                this.lists[this.editTask].text=this.list;
                 this.editTask=null;
            }
            this.list=''
        },
        remove(index){
            this.lists.splice(index, 1)
        },
        edit(index){
            this.list=this.lists[index].text;
            this.editTask=index;
        }
    }
}
</script>
