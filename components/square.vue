<template>
    <div>
        <div v-if="!isArrow" class="circle-wrapper">
            <div class="circle" v-bind:style="{ backgroundColor: color}">
                
            </div>
        </div>
        <div v-else>
            <div class="circle-with-arrow" v-bind:style="{ color: color}">
                <img class="arrow-img" v-if="color === 'red'" src="red_arrow.png"
                v-bind:style="checkDirection()">
                <img class="arrow-img" v-if="color === 'yellow'" src="yellow_arrow.png"
                v-bind:style="checkDirection()">
                <img class="arrow-img" v-if="color === 'green'" src="green_arrow.png"
                v-bind:style="checkDirection()">
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        props:{
            color:{
                type:String,
                required:true,
            },
            isArrow:{
                type:Boolean,
                required:true,
            },
            arrowDirection:{
                type:String,
                required:true,
            }
        },
        methods:{
            checkDirection(){
                if(this.arrowDirection === 'left'){
                    return { transform: 'rotate(-90deg)'}
                }
                if(this.arrowDirection === 'right'){
                     return { transform: 'rotate(90deg)'}
                }
                else  return {}
            }
        }
    }
</script>