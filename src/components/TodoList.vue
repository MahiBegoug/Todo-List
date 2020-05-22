<template>
    <div>
        <BaseInputText
            v-model="newTodoText"
            placeholder="New Todo"
            @keydown.enter="addTodo"
        />

        <ul v-if="todos.length">
            <TodoListItem
                v-for="todo in todos"
                :key="todo.id"
                :todo="todo"
                @remove="removeTodo"
            />
        </ul>
        <p v-else>
            Nothing left in the list. Add a new todo in the input above.
        </p>

    </div>
</template>

<script>
    import BaseInputText  from "@/components/BaseInputText";
    import TodoListItem from "@/components/TodoListItem";
    // import TodoListItem from "@/components/TodoListItem";
    let nextTodoId = 1
    export default {
        name: "TodoList",
        components:{
            TodoListItem,
            BaseInputText
        },
        data() {
            return {
                newTodoText:'',
                todos:[
                    {
                      id:nextTodoId++,
                      text:'Learn Vue'
                    },
                    {
                      id:nextTodoId++,
                      text:'Learn about single-file components'
                    },
                    {
                      id:nextTodoId++,
                      text:'Learn about Js'
                    }

                ]
            }
        },
        methods:{
            addTodo() {
                const trimmedText = this.newTodoText.trim()
                if (trimmedText){
                    this.todos.push({
                        id:nextTodoId++,text:trimmedText
                    })
                    this.newTodoText = ''
                }
            },
            removeTodo(idTodoRemove){
                this.todos = this.todos.filter(todo => {
                    return todo.id !== idTodoRemove
                })
            }
        }
    }
</script>

<style scoped>

</style>