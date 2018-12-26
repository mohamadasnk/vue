<template>
     <div class="test">
         <input type="text" v-model="title">

         <h1>{{title}}</h1>
          <small v-if="showName"> {{user.first_name}}</small>
          <small v-if="showName"> {{user.last_name}}</small>
          <small v-else> no body</small>
          <h4 v-for="item in items"> {{item.title}} </h4>

         <button v-on:click="greet('hello dear')"> say hi</button>
         <br>

         <input type="text" v-on:keyup="prss" v-on:keyup.shift="crtl">
         <br>
         <label for="">name</label>

         <input type="text" v-model="user.first_name">
         <br>


         <label for="">last</label>
         <input type="text" v-model="user.last_name">
         <br>
         <br>
         <br>
         {{fullname}}
         <br>
         <br>
         <br>
         {{msg}}
     </div>
</template>

<script>
    export default {
        name: "test",
        props:{

            msg:{
                type:String,

                default : 'footer'


            }


        },
        data(){

        return{

            title:'hello ali',
            user: {
                first_name:'ali',
                last_name:'azizi'



            },
            showName: true,
            items:[

                {title:'product one'},
                {title:'product two'},
                {title:'product three'}



            ]

        }


        },
        methods:{
            greet: function (gre) {
                alert(gre);
            },
            prss: function (e) {
                console.log(e.target.value);
            },
            crtl: function () {
                console.log('hi ali');
            }

        },
        computed:{
            fullname: function () {
                return this.user.first_name + ' '+ this.user.last_name;
            }
        }

    }
</script>

<style scoped>

</style>