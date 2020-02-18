<template>
  <div>
    <h1>Welcome to the Forum</h1>
    <div v-for="thread in threads">
      <h2>{{thread.title}}</h2>
      <div v-for="postId in thread.posts">
        <p>{{users[posts[postId].userId].name}}</p>
        <p>{{posts[postId].text}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import dataSource from '@/data.json'
console.log(dataSource)
export default {
  data () {
    return {
      threads: dataSource.threads,
      posts: dataSource.posts,
      users: dataSource.users
    }
  }
}
</script>
