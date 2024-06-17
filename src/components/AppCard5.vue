<template>
  <div class="card">
    <div class="card-body">
      <span class="badge bg-secondary">{{ typeName }}</span> 
      <h5 class="card-title mt-2">{{ title }}</h5>
      <p class="card-text">{{ contents }}</p>
      <a href="javascript:void(0);" class="btn" :class="isLikeClass" v-on:click="toggleLike">좋아요</a>
      <br />
      {{ obj }}
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    type: {
      type: String,
      default: 'news',
      validator: value => {
        return ['news', 'notice'].includes(value);
      }
    },
    title: {
      type: String,
      required: true,
    },
    contents: {
      type: String,
      required: true,
    },
    isLike: {
      type: Boolean,
      default: false,
    },
    obj: {
      type: Object,
      default: () => {},
    },
  },
  emits: ['toggleLike1'],
  setup (props, context) {
    console.log('props.title:', props.title);
    const isLikeClass = computed(() =>
      props.isLike ? 'btn-danger' : 'btn-outline-danger',
    );
    const typeName = computed(()=> {
      return props.type === 'news' ? '뉴스' : '공지사항';
    });


    const toggleLike = () => {
      //props.isLike = !props.isLike; // [Vue warn] Set operation on key "isLike" failed: target is readonly.
      //props.obj.title = '김길동';   // 하위컴포넌트에서 상위컴포넌트의 속성값을 바로 바꾸려고 해선 안된다.
      context.emit('toggleLike1');
    };


    return {
      isLikeClass,
      typeName,
      toggleLike,
    };
  }
}
</script>

<style scoped>

</style>