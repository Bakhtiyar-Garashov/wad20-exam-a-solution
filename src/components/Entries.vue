<template>
<div class="main">
    <button v-if="new2old" @click="new2old=!new2old">Newest to Oldest</button>
    <button v-else-if="!new2old" @click="new2old=!new2old">Oldest to newest</button>
   <div v-if="new2old">
        <ul :key="entry.id" v-for="entry in newToOldest" class="list-entries">
        <li>
            <h3>{{entry.title}}</h3>
            <p>{{entry.date|prettifyDate }}</p>
            <img :src="entry.image" alt="Entry image" srcset="">
            <p>{{entry.text}}</p>
            <hr>
        </li>
    </ul>
   </div>

   <div v-if="!new2old">
         <ul :key="entry.id" v-for="entry in oldestToNew" class="list-entries">
        <li>
            <h3>{{entry.title}}</h3>
            <p>{{entry.date|prettifyDate }}</p>
            <img :src="entry.image" alt="Entry image" srcset="">
            <p>{{entry.text}}</p>
            <hr>
        </li>
    </ul>

   </div>

</div>
</template>

<script>
    export default {
        name: 'Entries',
        props: {
            entries: Array
        },

        data:function(){
            return {
                new2old:true // default ordering is new to old
            }
        },
       
        filters:{
            prettifyDate:function(value){
                var datetime=new Date(value);
                var datepretty=datetime.toDateString();
                var timepretty=datetime.toLocaleTimeString();
                return datepretty+" "+timepretty
            }
        },
        computed:{
            // there will be some other ways to write the same functionality more "cleaner" way but for now it works :)
            newToOldest:function(){
                return this.entries.slice().sort((a,b)=>new Date(b.date)-new Date(a.date)) // slice is for not mutating actual array (throws error)
            },
            oldestToNew:function(){
                return this.entries.slice().sort((a,b)=>new Date(a.date)-new Date(b.date)) // slice is for not mutating actual array (throws error)
            }
        },
       

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
