<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h3>강의가 있습니까?</h3>
    <!--<p>{{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p>-->
    <p>{{ hasLecture }}</p>
    <p>{{ hasLecture }}</p>
    <p>{{ existLecture() }}</p>
    <p>{{ existLecture() }}</p>
    <button v-on:click="counter++">counter : {{ counter }}</button>
    <hr>
    <h2>이름</h2>
    {{ fullName }}
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup () {
    const teacher = reactive({
      name: 'kim',
      lectures: ['HTML/CSS', 'JavaScript', 'Vue3']
    })

    const hasLecture = computed(()=>{
      console.log("computed");
      return teacher.lectures.length > 0 ? '있음' : '없음';
    });
    
    const existLecture = () => {
      console.log("method");
      return teacher.lectures.length > 0 ? '있음' : '없음';
    }

    const counter = ref(0);

    const firstName = ref('길동');
    const lastName = ref('홍');

    /*
    const fullName = computed(()=>{
      return firstName.value + ' ' + lastName.value;
    });
    const fullName = computed( ()=> firstName.value + ' ' + lastName.value );
    */

    const fullName = computed({
      get() {
        return firstName.value + ' ' + lastName.value;
      },
      set(value) {
        /*
        console.log( 'value :' , value)
        console.log( value.split(' ') );
        const [first, last] = value.split(' ');
        console.log('first:' + first);
        console.log('last:'+ last);
        */
        
        [firstName.value, lastName.value] = value.split(' ');
      },
    });
    fullName.value = "송이 김";

    return { 
      teacher,
      hasLecture,
      existLecture,
      counter,
      fullName,
    }
  }
}
</script>

<style scoped>

</style>