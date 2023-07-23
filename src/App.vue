<script setup>
import { ref, reactive } from 'vue'

const fullImage = ref('https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60')
const images = [
  {
    thumb: "https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxfHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60"
  },
  {
    thumb: "https://images.unsplash.com/photo-1682695794816-7b9da18ed470?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDZ8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=300&q=60",
    full: "https://images.unsplash.com/photo-1682695794816-7b9da18ed470?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60"
  },
  {
    thumb: "https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE4fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60"
  },
  {
    thumb: "https://plus.unsplash.com/premium_photo-1666963323736-5ee1c16ef19d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://plus.unsplash.com/premium_photo-1666963323736-5ee1c16ef19d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60"
  }
]


let i = ref(0)
function showNextImage(){
  i.value < images.length-1 ? ++i.value: i.value = images.length-1
  fullImage.value = images[i.value].full
}
function showPrevImage(){

// console.log(images[i],i)
i.value > 0 ? --i.value: i.value
fullImage.value = images[i.value].full
}


</script>


  <template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity</h1>
    <div class=" flex gap-3 justify-end">
      
      <button @click="showPrevImage()" :disabled="i == 0" class="disabled:bg-slate-200 disabled:text-slate-300 bg-green-500 text-slate-100 hover:bg-slate-400 focus:outline-none focus:border-none">
      
        <span>
          <i class="fa-solid fa-arrow-left"></i>
        </span>
      </button>
      
      <button @click="showNextImage()" :disabled="i == images.length-1"  class="disabled:bg-slate-200 disabled:text-slate-300 bg-green-500 text-slate-100 hover:bg-slate-400 focus:outline-none focus:border-none">
      
      <span>
        <i class="fa-solid fa-arrow-right"></i>
      </span>
      </button>
    </div>
    
      <div class="mt-12">
        <img  class="cursor-pointer w-full h-80" :src="fullImage" >
      </div>
  </section>

</template>

<style scoped>

</style>
