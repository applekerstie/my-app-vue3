<template>
  <div>
    <h2>input value</h2>
    <hr />

    <input type="text" v-model="inputValue" />

    <!--
    <input type="text" :value="inputValue"
    v-on:input="event => (inputValue = event.target.value)"
    />
    -->
    <p>{{ inputValue }}</p>

    <hr />

    <textarea v-model="textareaValue"></textarea>
    <!--
    <textarea :value="textareaValue"
    v-on:input="event => (textareaValue = event.target.value)"
    ></textarea>
    -->
    <p>{{ textareaValue }}</p>

    <hr />
    <h2>checkbox value</h2>
    <label for="checkbox">
    {{ checkboxValue }}
    <input type="checkbox" id="checkbox" v-model="checkboxValue" />
    <!--
    <input type="checkbox" id="checkbox" :checked="checkboxValue"
    v-on:change="event => (checkboxValue = event.target.checked)"
    >
    -->
    </label>
  </div>

  <hr />

  <h2>radio value</h2>
  <div>
    <label>
      <input type="radio" name="type" value="o" 
      :checked="radioValue1 === 'o'" 
      v-on:change="event => (radioValue1 = event.target.value)"
      />
      o
    </label>
    <label>
      <input type="radio" name="type" value="x" 
      :checked="radioValue1 === 'x'" 
      v-on:change="event => (radioValue1 = event.target.value)"
      />
      x
    </label>
    <p>{{ radioValue1 }}</p>
  </div>
  <div>
    <label>
      <input type="radio" name="type2" value="o" v-model="radioValue2" />
      o
    </label>
    <label>
      <input type="radio" name="type2" value="x" v-model="radioValue2" />
      x
    </label>
    <p>{{ radioValue2 }}</p>
  </div>
  <hr />

  <h2>select value</h2>
  <select v-model="selectValue">
  <!-- 
  :value="selectValue"
  v-on:change="event => (selectValue = event.target.value)"
  >
  -->
    <option value="html">html</option>
    <option value="css">css</option>
    <option value="javascript">javascript</option>
  </select>
  <p>{{ selectValue }}</p>

  <hr />
  <label for="checkbox2">{{ checkboxValue2 }}
    <input type="checkbox" id="checkbox2"
    v-model="checkboxValue2"
    true-value="Yes"
    false-value="No"
    >
  </label>

  <hr />
  <h2>checkbox values</h2>
  <label>
    <input type="checkbox" value="html" v-model="checkboxValues" />
    html
  </label>
  <label>
    <input type="checkbox" value="css" v-model="checkboxValues" />
    css
  </label>
  <label>
    <input type="checkbox" value="javascript" v-model="checkboxValues" />
    javascript
  </label>
  <p>{{ checkboxValues }}</p>

  <hr />
  <input type="text" v-model.lazy="inputValue2">
  <p>{{ inputValue2 }}</p>

  <hr />
  <input type="text" v-model.number="inputValue3" />
  <p>{{ inputValue3 }}</p>
  <p>{{ typeof inputValue3 }}</p>

  <hr />
  

</template>

<script>
import { ref } from 'vue';

export default {
  setup () {
    const inputValue = ref(null);
    const textareaValue = ref(null);
    const checkboxValue = ref(true);
    const checkboxValue2 = ref(true);
    const radioValue1 = ref('o');
    const radioValue2 = ref('x');
    const selectValue = ref('javascript');

    const checkboxValues = ref([]);
    const inputValue2 = ref(null);
    const inputValue3 = ref(null);

    return {
      inputValue,
      inputValue2,
      inputValue3,
      textareaValue,
      checkboxValue,
      checkboxValue2,
      checkboxValues,
      radioValue1,
      radioValue2,
      selectValue,
    }
  }
}
</script>

<style scoped>
hr {
  margin: 30px 0;
}
</style>