<template>
  <div class="card">
    <div class="card-body">
      <span class="badge bg-secondary">
        {{ typeName }}
      </span>
      <h5 class="card-title mt-2">{{ title1 }}</h5>
      <p class="card-text">{{ contents1 }}</p>
      <a 
      href="javascript:void(0);" 
      class="btn" 
      :class="isLikeClass"
      v-on:click="toggleLike"
      >
      좋아요</a>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    title1: {
      type: String,
      required: true,
    },
    contents1: {
      type: String,
      required: false,
    },
    postType1: {
      type: String,
      default: 'news',
    },
    isLike1: {
      type: Boolean,
      required: false,
    }
  },
  setup (props, context) {
    const typeName = computed(() => {
      return props.postType1 === 'news' ? '뉴스' : '공지사항';
    });
    
    const isLikeClass = computed(() => {
      return props.isLike1 ? 'btn-danger' : 'btn-outline-danger';
    });

    const toggleLike = () => {
      context.emit('toggleLike2');
    }

    return {
      typeName,
      isLikeClass,
      toggleLike,
    }
  }
}
</script>

<style scoped>

</style>