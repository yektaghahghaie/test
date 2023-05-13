<template>
  <section class="New Article">
    <div class="flex w-1440 h-16 bg-gry4 pt-2.5 pr-7 pb-2.5 pl-4">
        <div class="text-gry2 mt-1.5 mr-0.5 mb-1.5 ml-0 text-2xl w-44 h-7">Arvan Challenge</div>
        <div class="text-base text-gry2 h-5 w-44 mt-3 mr-953 mb-3 ml-5">Welcome username </div>
        <button class="mr-0 rounded border border-solid text-blue2 border-blue2 h-10 w-20" type="submit">Logout</button>
    </div>
    <div class="flex">
        <div class="w-64 h-964 mr-8 mt-0 mb-0 ml-0 pt-3 pr-0 pb-817 pl-3 bg-blue">
            <div class="w-11 h-7 text-2xl text-gry2 mt-0 mr-48 mb-7">Post</div>
            <button><router-link to="/All" class="w-24 h-5 text-gry2 text-lg mt-0 mr-32 mb-4 ml-3.5">All Articles</router-link></button>
            <button type="submit" class="w-24 h-5 text-gry2 text-lg mt-0 mr-32 mb-4 ml-3.5">New Article</button>
        </div>
        <div class="mt-6">
            <div class="text-black text-4xl mb-7">New Article</div>
            <form @submit.prevent="add">
            <label class="mb-1.5 text-base" for="Title">Title</label>
            <br>
            <input type="text" placeholder="Title" class=" mb-1.5 text-base w-848 h-10 rounded bg-gry2 border border-solid border-red pl-2.5 mt-2 mr-0 ml-0" v-model="Title">
            <p class="mb-4 text-base">Required field</p>
            <label class="mb-1.5 text-base" for="Description">Description</label>
            <br>
            <input type="text" placeholder="Description" class="text-base w-848 h-10 rounded bg-gry2 border border-solid border-red pl-2.5 mt-2 mr-0 ml-0" v-model="Description">
            <p class="mb-1.5 text-base mt-6">Body</p>
            <input type="text" class="w-848 h-52 mt-2 mr-0 mb-0 rounded bg-gry2 border border-solid border-gry3" v-model="Body">
            <br>
            <button class="w-24 h-8 rounded border border-solid border-blue bg-blue mt-6 mr-770 mb-5 ml-1 pt-1 pr-7 pb-2 pl-6 text-gry2">Submit</button>
            </form>
            </div>
        <div class="mt-24">
            <label class="w-8 h-5 text-base mt-0.5 mr-60 mb-8 ml-8" for="Tags">Tags</label>
            <input type="text" placeholder="New tag" class="w-64 h-10 rounded border border-solid border-gry3 bg-gry2 mt-0.5 mr-7 mb-1.5 ml-8 pt-3 pr-44 pb-3 pl-3">
            <div class="w-64 h-366 rounded border border-solid border-gry3 bg-gry2 mt-4 mr-7 mb-4 ml-8 pt-4 pr-48 pb-4 pl-4">
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
                <input class="mb-4" type="checkbox" name="tag">
                <label for="Tag">Tag</label>
            </div>
        </div>
    </div>
</section>
</template>

<script>
export default {
  data(){
    return{
      Title:'',
      Description:'',
      Body:'',
    }
  },
methods:{
  newarticle(){
    let project={
        title:this.title
    }
    axios.delete('https://conduit.productionready.io/api/articles')
  .then(res=>{
    this.articles=res.data.data;
  })
  .then(()=>{
    this.$router.push('/all')
  })
  .catch(err=>{
    console.log(12,err);
  })
},
add(){
  let art={
  Title:this.Title,
      Description:this.Description,
      Body:this.Body,
  }
  this.$router.push('/All')
}
}
}
</script>

<style>

</style>