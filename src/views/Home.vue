<template>
    <div class="container">
            <div class="todos">
                <div class="header flex">
                    <div class="task">4 Tasks</div>
                    <div class="remain">4 Remain</div>
                </div>
                <div>
                <todo-list/> 
                </div>
            </div>
        </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import TodoList from '../components/Todolist.vue';

@Component({
  components: {
    TodoList,
  },
})
export default class Home extends Vue {}
</script>

<style lang="css">
  * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        #app {
            background-color: #f8768d;
            font-family: "Roboto", sans-serif;
        }
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .todos {
            width: 400px;
            background-color: #fff;
            padding: 0 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 4px 4px rgba(0, 0, 0, 0.3);
        }
        .flex {
            display: flex;
        }
        .header {
            padding: 30px 0;
            justify-content: space-around;
            font-size: 24px;
            font-weight: 600;
            border-bottom: 1px solid #ccc;
        }
        .todo-list {
            margin: 30px 0;
        }
        .todo-item {
            margin: 30px 0;
            justify-content: space-between;
            font-size: 20px;
        }
        .a {
            display: flex;
            align-items: center;
        }
        .a input {
            margin-right: 10px;
        }
        .delete-todo {
            padding: 2px 10px;
            border-radius: 10px;
            border: 1px solid #000;
            outline: none;
            background-color: #fff;
        }
        .delete-todo:hover {
            background-color: orangered;
        }
        .footer {
            display: flex;
            justify-content: space-around;
            margin: 20px 0;
        }
        .input {
            width: 300px;
            border-radius: 10px;
            border: 1px solid #000;
            padding: 10px;
            outline: none;
        }
</style>