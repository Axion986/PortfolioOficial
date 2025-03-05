<template>
  <figure class="p-6">
            <img
                class="w-32 h32 rounded-full mx-auto"
                :src="photo"
                alt="profile picture"
                width="400"
                height="400"
            />
            <figure class="pt-6 text-center space-y-4">
                <figcaption class="font-medium">
                    <div class="text-cyan-900 text-xl"> {{title}}</div>
                    <div class="text-gray-500 font-light">{{ subtitle }}</div>
                </figcaption>
                <blockquote>
                    <p class="text-lg-font-medium"> Eng.Produção | Lean Black Belt Six Sigma | Eng. Software</p>
                </blockquote>
            </figure>
        </figure>

</template>

<script setup>
    const { photo,title,subtitle}= defineProps (["photo",'title',"subtitle"]);
</script>