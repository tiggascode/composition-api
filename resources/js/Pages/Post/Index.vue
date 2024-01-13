<template>
    <div class="mx-auto w-1/2" >
        <div class="mb-4">
            Post Index
        </div>
        <div  class="mb-4">
            {{ str }}
        </div>
        <div  class="mb-4">
            <a @click.prevent="changeStr" href="" class="inline-block px-3 py-2 bg-sky-600 border border-sky-700 text-white">Say Hello</a>
        </div>
        <div  class="mb-4">
            <div v-for="item in computedArr"> {{ item }} </div>
        </div> 
    </div>
</template>

<script>
import {ref, reactive} from "@vue/reactivity"
import {computed, watch} from "vue"
export default {
    name: 'Index',

    setup (){
        //data
        const str = ref('some string')

        const someArr = reactive([1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 ])


        // methods

        const changeStr = function (){
            str.value = 'new string' 
        }

        // computed 
        const computedArr = computed(() => {
            return someArr.filter(item => item%2 === 0)
        })
        
        // watch
        watch(str, function () {
            console.log(11111)
        })

        return {str, changeStr,computedArr}
    }
}

</script>

<style scoped>

</style>