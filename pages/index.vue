<template>
<div class="main">
  <div class="whole-list-wrapper">
    <div style="max-width:800px;">
      <div class="result">
        <div class="image-result-wrapper">
          <traffic-light :type="type" :direction="direction"></traffic-light>
        </div>
        <div class="text-result-wrapper">
          <div>
              <b>{{type}}</b> .М.4 Ж.1.ГИ3
          </div>
          <div>
            Размер апертуры: 200мм
          </div>
          <div>
            С устройством звукового сопровождения
          </div>
          <div>
            С правой дополнительной секцией
          </div>
          <div>
            С козырьком
          </div>
          <div>
            С жёлтым кругом
          </div>
          <div>
            <button class="button">
              Сохранить в PDF
            </button>
          </div>
          <div>
            <button class="button">
              Сохранить картинку
            </button>
          </div>
        </div>
      </div>
      <div class="columns">
        <div class="column">
        <div>
          <label>Тип 1
             <input name="type" type="radio" value="T1" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 2
              <input name="type" type="radio" value="T2" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 3
              <input name="type" type="radio" value="T3" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 4
              <input name="type" type="radio" value="T4" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 6
              <input name="type" type="radio" value="T6" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 7
              <input name="type" type="radio" value="T7" v-model="type">
          </label>
        </div>
        <div>
          <label>Тип 8
              <input name="type" type="radio" value="T8" v-model="type">
          </label>
        </div>
        <div>
           <label>Тип 10
                <input name="type" type="radio" value="T10" v-model="type">
           </label>
        </div>
        <div>
          <label>Тип 11
             <input name="type" type="radio" value="T11" v-model="type">
          </label>
        </div>
        <div>
          <label>ТДС
             <input name="type" type="radio" value="TDS" v-model="type">
          </label>
        </div>
        </div>
        <div class="column" v-if="type ==='T2' || type === 'TDS'">
          <div>
          <label>Лево
             <input name="direction" type="radio" value="left" v-model="direction">
          </label>
        </div>
         <div>
          <label>Право
             <input name="direction" type="radio" value="right" v-model="direction">
          </label>
        </div>
        <div>
          <label>Прямо
             <input name="direction" type="radio" value="" v-model="direction">
          </label>
        </div>
        </div>
      </div>
    </div>
  </div>
  <div class="table-wrapper">
    <div class="columns" v-for="(item,index) in items" :key=index>
        <div class="column">
          {{item.a}}
        </div>
        <div class="column">
          {{item.b}}
          <div class="circle" style="background-color:red;">

          </div>
        </div>
        <div class="column">
          {{item.c}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TrafficLight from '~/components/TrafficLight.vue'

export default {
  components: {
    TrafficLight,
  },
  data:function(){
    return{
      type:'',
      direction:'',
      items:[{a:1,b:2,c:3},{a:4,b:5,c:6},{a:7,b:8,c:9}],

    }
  },
}
</script>
