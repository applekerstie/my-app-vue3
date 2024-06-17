<template>
  <div>
    <form action="" v-on:submit.prevent="save(textValue, textareaValue)">
      <div>
        <input type="text" v-model.lazy="textValue" placeholder="Title" />
      </div>
      <div>
        <textarea v-model.lazy="textareaValue" placeholder="Contents"></textarea>
      </div>
      <hr />
      <button>저장</button>
    </form>
  </div>

  <div>
    <form action="" v-on:submit.prevent>
      <div>
        <input type="text" v-model.lazy="textValue2" placeholder="Title" />
      </div>
      <div>
        <textarea v-model.lazy="textareaValue2" placeholder="Contents"></textarea>
      </div>
      <hr />
      <button v-on:click="save(textValue2, textareaValue2)">저장</button>
    </form>
  </div>
</template>

<script>
import { ref, watchEffect } from 'vue';

export default {
  setup () {
    const textValue = ref('');
    const textareaValue = ref('');

    const save = function (title, contents){
      console.log(`저장되었습니다 title: ${title}, contents: ${contents}`);
    }

    watchEffect( ()=>{
      console.log('watcheffect', textValue.value, textareaValue.value);
      //save( textValue.value, textareaValue.value);
    } );


    const textValue2 = ref('');
    const textareaValue2 = ref('');


    return {
      textValue,
      textareaValue,
      textValue2,
      textareaValue2,
      save,
    }
  }
}
</script>

<style scoped>

</style>