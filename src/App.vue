<template>
  <main class="font-body min-h-screen min-w-screen sm:bg-charcoal-gray sm:flex sm:justify-center sm:items-center">
    <Success
      v-if="email"
      @dismissed="email = null"
      :email="email"
    />
    <Subscribe 
      v-else
      @subscribed="(v) => (email = v)"
    />
  </main>
</template>

<script>
  import Subscribe from "@/components/Subscribe";
  import Success from '@/components/Success'

  export default{
    name: 'App',
    components: {
      Subscribe,
      Success,
    },
    data(){
      return{
        email: null,
      };
    },
  };
</script>
