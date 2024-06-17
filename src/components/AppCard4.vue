<template>
  <div class="card">
    <div class="card-body">
      <!--
      <span class="badge bg-secondary">{{ type === 'news'? '뉴스' : '공지사항' }}</span>
      -->
      <span class="badge bg-secondary">{{ typeName }}</span>
      
      <h5 class="card-title mt-2">{{ title }}</h5>
      <p class="card-text">{{ contents }}</p>

      <!--
      <a v-if="isLike" href="#" class="btn btn-danger">좋아요</a>
      <a v-else href="#" class="btn btn-outline-danger">좋아요</a>
      -->
      <a href="#" class="btn" :class="isLikeClass" v-on:click="toggleLike">좋아요</a>
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
      //default: {} // 이렇게 하면 안됨. 디폴트 선언시 기본값을 반환하는 팩토리 함수형태로 선언해줘야함
      /*
      default: function() {
        return {}
      },
      */
     default: () => { // arrow 함수로 변경

     }

    }

  },
  setup (props) {
    console.log('props.title:', props.title);
    const isLikeClass = computed(() =>
      props.isLike ? 'btn-danger' : 'btn-outline-danger',
    );
    const typeName = computed(()=> {
      return props.type === 'news' ? '뉴스' : '공지사항';
    });


    const toggleLike = () => {
      //props.isLike = !props.isLike; // [Vue warn] Set operation on key "isLike" failed: target is readonly.
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