<template>
    <div class="screen">
        <div class="main-part">
            <Square 
            v-if="this.type !=='T7' 
            && this.type !== 'T10'
            && this.type !== 'T11'
            && this.type !== 'TDS'" 
            color="red" 
            :isArrow="shouldDrawArrow"
            :arrowDirection="direction"></Square>
            <Square 
            v-if="this.type !=='T6' 
            && this.type !== 'T8' 
            && this.type !== 'T10' 
            && this.type !== 'T11'
            && this.type !== 'TDS'" 
            color="yellow" 
            :isArrow="shouldDrawArrow"
            :arrowDirection="direction"></Square>
            <Square 
            v-if="this.type !=='T6'
             && this.type !== 'T7' 
             && this.type !== 'T10'" 
             color="green" 
             :isArrow="shouldDrawArrow"
             :arrowDirection="direction"></Square>
            <Square
             v-if="this.type ==='T10'"
             color="white"
             :isArrow="false"></Square>
        </div>
    </div>
</template>
<script>
    import Square from './square';
    export default{
        props:{
            type:{
                type:String,
                required:true,
            },
            direction:{
                type:String,
                required:true,
            },
        },
        data:function(){
            return{
               shouldDrawArrow : false, 
            }
        },
        components:{
            Square,
        },
        watch: { 
            type: function(newVal, oldVal) { 
            if(newVal === 'T2' || newVal === 'TDS'){
                this.shouldDrawArrow = true;
            }
            else{
                this.shouldDrawArrow = false;
            }
      },
        }
    }
</script>