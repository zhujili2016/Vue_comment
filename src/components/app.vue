<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对React的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <add :add-comment="addComment"></add>
      <list :comments="comments" :delete-comment="deleteComment"></list>
    </div>
  </div>
</template>
<script>
  import add from "./add.vue";
  import list from "./list.vue";
  export default {
    data () {
      return {
        comments:[]
      }
    },
    created(){
      setTimeout(()=>{
        const comments = [
          {
            username:"小莉",
            content:"react真不错！！"
          },
          {
            username:"小龙",
            content:"vue真不错！！"
          }
        ];
        this.comments = comments;
      },2000)
    },
    methods:{
      addComment(comment){
        this.comments.unshift(comment)
      },
      deleteComment(index){
        this.comments.splice(index,1)
      }
    },
    components: {
      add,
      list
    }
  }
</script>
<style>

</style>
