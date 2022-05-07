<template>
  <div class="wrapper">
    <!-- header -->
    <div class="wrapper-content">
      <div class="view">
        <div class="container">
          <Form @add-tweet="handleTweet" />
          <List :items="items"/>
        </div>
      </div>
    </div>
    <!-- footer -->
  </div>
</template>

<script>
import Form from '@/components/Form'
import List from '@/components/List'
export default {
  components: {
    Form,
    List
  },
  data () {
    return {
      items: [
        {
          id: 1,
          body: 'hello vue 3',
          avatar: `https://avatars.dicebear.com/api/male/john.svg`,
          likes: 12,
          date: new Date(Date.now()).toLocaleString()
        },
        {
          id: 2,
          body: 'hello world',
          avatar: `https://avatars.dicebear.com/api/female/2.svg`,
          likes: 8,
          date: new Date(Date.now()).toLocaleString()
        }
      ]
    }
  },
  methods: {
    handleTweet (item) {
      this.items.push(item)
    }
  }
}
</script>
