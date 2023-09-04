<script setup>
const { data: posts } = await useAsyncData('latest-posts', () =>
  queryContent('/blog')
    .sort({ data: 1 })
    .limit(3)
    .find()
)
</script>


<template>
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8 mt-8 ">
    <section class="text-gray-900 py-2 ">
        <h1 class="text-5xl font-bold">Hello, I am Famid hasan konok</h1>
        <p class="text-base text-gray-700 p-2 italic">Spring Devloper Advocate at VMware</p>
    </section>
    <section class="flex flex-col md:flex-row">
        <div class="md:w-3/4">
            <h2 class="text-3xl font-bold mt-8">My Story</h2>
            <p class="text-lg py-2">
                I am Software Engineer living just outside of one of my favorite place in the world,
                Bangladesh,Dhaka. I am a self-taught progammer who firmly belive that you can accomplish anything in the
                life if you put your mind to it, roll up your sleeves and willing to put in the work.
            </p>
            <p class="text-lg py-2">
                I have been writting Software for over 20+ years now I use my knowledge, passion, and influence to help
                other developers achieve their goals. I teach online and currently, have over 160,000 student
            </p>
            <p class="text-lg py-2">
                In my personal life I am a husbant to my best friend in the world and a father of my two little girls. I
                enjoy reading running and lifting weights to get me through the week. </p>
        </div>
        <img src="~/assets/images/portfolioImg.png" alt="MyPhoto" class="w-1/2 md:max-w-sm p-8 mx-auto">
    </section>

        <section class="mb-8">
            <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
            <div class="grid md:grid-cols-3 pt-8 gap-10">
              <Post :posts="posts" />
            </div>
          </section>
        
    </div>

</template>

<style  scoped></style>