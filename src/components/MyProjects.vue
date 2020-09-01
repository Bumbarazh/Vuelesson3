<template>
    <div>
        <input type="text"
               v-model="textOfTodo"
        placeholder="Input text">
        <button @click="addTodo">Add</button>
        <hr>
        <ol>
            <li v-for="(todo, i) in arrWithTodo"
                :key="i">
                {{todo}}
            <button @click="removeTodo(i)">Remove</button>
            </li>
        </ol>
    </div>
</template>

<script>


    export default {
        name: 'MyProjects',

        data () {
            return {
                textOfTodo: '',
                arrWithTodo: []
            }
        },

        beforeMount () {
        this.$http.get('https://vue-lesson-three.firebaseio.com/toDos.json')
            .then((res) => {
                // console.log(res, 'RESPONSE');
                return res.json()
            }).then((res) => {
            // console.log(res, 'JSON');
            res === null ? console.log(`res = ${res}`) : Object.values(res).forEach(u => this.arrWithTodo.push(u.text));
        })
    },

        methods: {
            addTodo () {
                this.arrWithTodo.push(this.textOfTodo);
                // this.textOfTodo = '';
                this.$http.post('https://vue-lesson-three.firebaseio.com/toDos.json', {text:this.textOfTodo})
                    // .then((res) => {
                    //           console.log(res);
                    //         }, error => {
                    //           console.log(error)
                    //         })
                this.textOfTodo = '';
            },
            removeTodo (i) {
                this.$http.get('https://vue-lesson-three.firebaseio.com/toDos.json')
                    .then((res) => {
                        return res.json()
                    }).then((res) => {

                    console.log(Object.keys(res)[i]);

                    this.$http.delete(`https://vue-lesson-three.firebaseio.com/toDos/${Object.keys(res)[i]}.json`)

                    this.arrWithTodo.splice(i, 1);
                })
            },
        }
    }
</script>

<style>

</style>
