<template>
  <Layout>
    <h1>{{ $page.tag.title }}</h1>
    <ul>
      <li v-for="edge in $page.tag.posts" :key="edge.id">
        <g-link :to="'/post/' + edge.id">
          {{ edge.title }}
        </g-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query($id:ID!){
  tag:strapiTag(id:$id){
    id
    title
    posts{
      id
      title
    }
  }
}
</page-query>

<script>
export default {
  name: 'TagPage',
}
</script>
