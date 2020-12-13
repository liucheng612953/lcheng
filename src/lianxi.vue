<template>
    <div id="app">
        <div v-for="(itme,index) in array " :key="index">
        <div v-bind:class="[array[index]==0?btn:array[index]==0?btn2:array[index]==0?btn3:btn4]">{{arr.id}}</div>
        <div>{{arr.title}}</div>
        <div>{{arr.number}}</div>
        </div>
        <!-- <div>
        <div v-bind:class="btn2">{{arr.id}}</div>
        <div>{{arr.title}}</div>
        <div>{{arr.number}}</div>
        </div>
        <div>
        <div v-bind:class="btn3">{{arr.id}}</div>
        <div>{{arr.title}}</div>
        <div>{{arr.number}}</div>
        </div> -->
    </div>
</template>
<script>
export default {
    array:[
        {
            id:1,
            title:"这个国家",
            number:"400万"
    },
     {
            id:2,
            title:"那个国家",
            number:"300万"
    },
     {
            id:3,
            title:"个国家",
            number:"200万"
    },
     {
            id:4,
            title:"国家",
            number:"100万"
    },
    ]
}
</script>
<style >
    .btn{
        color: rgb(241, 7, 7);
    }
    .btn2{
        color: rgb(218, 241, 7);
    }
    .btn3{
        color: rgb(241, 206, 7);
    }
    .btn4{
        color: rgb(10, 10, 10);
    }
</style>