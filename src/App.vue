<template>
  <div id="modifiers">
    <div @click="clickDiv">
      DIV 영역
      <p @click="clickP">
        P 영역
        <span @click="clickSpan">SPAN 영역</span>
        <a href="https://naver.com">a 영역</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  setup () {
    const clickDiv = () => {
      console.log('clickDiv');
      location.href = 'https://www.naver.com'
    }
    const clickP = () => {
      console.log('clickP');
    }
    const clickSpan = (e) => {
      console.log('clickSpan');
      e.stopPropagation();
      alert('좋아요')
    }

    return {
      clickDiv,
      clickP,
      clickSpan
    }
  }
}
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
  padding: 40px;
}
#modifiers div {
  background-color: #ccc;
}
#modifiers p {
  background-color: #999;
}
#modifiers span {
  background-color: #666;
  display: 'block';
}
</style>