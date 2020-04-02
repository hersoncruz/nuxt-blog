<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: {
    PostList
  },
  asyncData(context, callback) {
    console.log(context)
      setTimeout(() => {
        callback (null, {
          loadedPosts: [
            {
              id: '1',
              title: 'First post',
              previewText: 'This is our first post',
              thumbnail: 'https://www.freeimageslive.com/galleries/transtech/objects/pics/shiftkey00029.jpg'
            },
            {
              id: '2',
              title: 'Second post',
              previewText: 'This is our second post',
              thumbnail: 'https://www.freeimageslive.com/galleries/transtech/objects/pics/shiftkey00029.jpg'
            }
          ]
        });
      }, 1500)
  },
}
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
