<template>
  <div id="modifiers">
    <div @click="clickDiv">
      DIV 영역
      <p @click="clickP">
        P 영역
        <span @click.stop="clickSpan">SPAN 영역</span>
        <a href="https://naver.com" @click.prevent.stop="clickA">a 영역</a>
      </p>
    </div>
  </div>

  <a href="https://naver.com" @click.prevent="clickA">a 영역</a>

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
    const clickSpan = () => {
      console.log('clickSpan');
      //e.stopPropagation();
      alert('좋아요')
    }
    const clickA = () => {
      //e.preventDefault();
      alert('어떤기능');
    }

    return {
      clickDiv,
      clickP,
      clickSpan,
      clickA,
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