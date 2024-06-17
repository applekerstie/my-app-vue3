<template>
  <div class="container py-4">
    <h2>input value</h2>  
    <!-- value / input event -->
    <input type="text" class="form-control"
    :value="inputValue"
    v-on:input="event => (inputValue = event.target.value)"
    />
    <p>{{ inputValue }}</p>

    <hr class="mt-4" />

    <h2>textarea value</h2>
    <!-- value / input event -->
    <textarea class="form-control" rows="3"
    :value="textareaValue"
    v-on:input="event => (textareaValue = event.target.value)"
    >
    </textarea>
    <p>{{ textareaValue }}</p>

    <hr class="mt-4" />

    <h2>checkbox value</h2>
    <!-- checked / change event -->
    <div class="form-check">
      
      <input class="form-check-input" type="checkbox" id="flexCheckDefault"
      :checked="checkboxValue"
      v-on:change="event => ( checkboxValue = event.target.checked )"
      />
      
      <!--
      <input class="form-check-input" type="checkbox" id="flexCheckDefault"
      v-model="checkboxValue"
      true-value="Yes"
      false-value="No"
      />
      -->
      <label class="form-check-label" for="flexCheckDefault">
        {{ checkboxValue }}
      </label>
    </div>

    <hr class="mt-4" />

    <h2>checkbox values</h2>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="1" id="flexCheck1" v-model="checkboxValues" />
      <label class="form-check-label" for="flexCheck1">
        1
      </label>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="2" id="flexCheck2" v-model="checkboxValues" />
      <label class="form-check-label" for="flexCheck2">
        2
      </label>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="3" id="flexCheck3" v-model="checkboxValues" />
      <label class="form-check-label" for="flexCheck3">
        3
      </label>
    </div>
    <p>{{ checkboxValues }}</p>

    <hr class="mt-4" />

    <h2>radio value</h2>
    <!-- checked / change event -->
    <div>
      <label class="form-check-label" for="flexRadioDefault1"> 
        <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1"
        value="O"
        :checked="radioValue === 'O'"
        v-on:change="event => (radioValue = event.target.value)"
        />
        O
      </label>
    </div>

    <div>
      <label class="form-check-label" for="flexRadioDefault2"> 
        <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2"
        value="X"
        :checked="radioValue === 'X'"
        v-on:change="event => (radioValue = event.target.value)"
        />
        X
      </label>
    </div>
    <p>{{ radioValue }}</p>
    
    <hr class="mt-4" />

    <h2>select value</h2>
    <!-- value / change event -->
    <select class="form-select" 
    :value="selectValue"
    v-on:change="event => (selectValue = event.target.value)"
    >
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>
    <p>{{ selectValue }}</p>

  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup () {
    const inputValue = ref('');
    const textareaValue = ref('');
    const checkboxValue = ref(true);
    const radioValue = ref('O');
    const selectValue = ref('');
    const checkboxValues = ref([]);

    return {
      inputValue,
      textareaValue,
      checkboxValue,
      radioValue,
      selectValue,
      checkboxValues,
    }
  }
}
</script>

<style scoped>

</style>