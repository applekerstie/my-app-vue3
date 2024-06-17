<template>
  <div>

  </div>
</template>

<script>
import { ref, watch, reactive } from 'vue';

export default {
  setup () {
    const x = ref(0);
    const y = ref(0);

    /*
    watch( function(){
      return x.value + y.value;
    }, 
    (newSum, oldSum) => {
      console.log( 'newSum:', newSum);
      console.log( 'oldSum:', oldSum);
    });
    */
    /*
    watch( () => x.value + y.value, (newSum) => {
      console.log('newSum:', newSum)
    })
    */
    /*
    watch( [x,y], ([newX, newY]) => {
      console.log(newX, newY);
    } );
    */

    
    const obj = reactive({
      count: 0,
    });

    /*
    watch(obj, (newObj, oldObj) => {
      console.log('newObj:', newObj);
    });
    */

    // 아래처럼 하면 감지안됨
    /*
    watch(obj.count, (newObj) => {
      console.log('newObj:', newObj);
    }
    );
    */
    
    // 특정 obj 의 속성을 감지하려면 getter 사용
    watch(
      () => obj.count,
      (newObj, oldObj) => {
        console.log('1 newObj:', newObj);
      }
    );

    const person = reactive({
      name: '홍길동',
      age: 30,
      hobby: '운동',
      obj: {
        count: 0,
      },
    });

    watch(
      () => person.obj.count,
      newObj => {
        console.log('2 newObj:', newObj);
      }
    )
    

    return {
      x, y, obj, person
    }
  }
}
</script>

<style scoped>

</style>