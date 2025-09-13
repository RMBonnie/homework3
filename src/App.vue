<script setup>
  import {ref} from 'vue'
  
  const myArray = ref([])
  const name = ref('')
  const input_content = ref('')
  const input_category = ref(null)

  const addTodo = () =>{
    if(input_content.value.trim() === '' || input_category.value === null) { 
      return
    }

    myArray.value.push({
      content: input_content.value,
      category: input_category.value,
    })

    input_content.value = ''
    input_category.value = null
  }

</script>

<template>

  <main class="app">
    
    <section class="greeting">
      <h2 class="class">
        Welcome back, <input type="text" placeholder="Enter Name" v-model="name">
      </h2>

    </section>

    <section class="create-todo">
      <h3>CREATE A TO DO LIST</h3>
      <form submist.prevent = "addTodo">
      <h4>That's on your to do list?</h4> 
      <input type="Text" placeholder="e.g., Make a Video" v-model="input_contnet"/>


    <h4>Pick a category</h4>
    <div class="options">
      <label>
        <input type="radio" name="category" value="business" v-model="input_category"></input>
        <span class="bubble buisness"></span>
        <div>Business</div>
      </label>
            <label>
         <input type="radio" name="category" value="personal" v-model="input_category"></input>
          <span class="bubble personal"></span>
          <div>Personal</div>
       </label>


      </div>
      <input type="submit" value="Add To Do"/>
     </form>
    </section>
    
    <secion class="todo-list">


    </secion>

  </main>


</template>

