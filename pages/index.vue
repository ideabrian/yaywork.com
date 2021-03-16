<template>
  <div class="container mx-auto max-w-xl py-20">
    <div class="mt-2">
      <h1 class="font-black text-4xl lg:text6xl leading-0">Independent Together</h1>
      <h2 class="mt-5 mb-5 text-lg lg:text-xl leading-3">Yay Work is a new way for independent creators to work.</h2>
      <h2 class="mt-5 mb-5 text-lg lg:text-xl leading-3">It's like Twitter, Slack, Product Hunt, and Upwork all blended into one. </h2>
    </div>
    <div class="mt-10">
      <h2 class="text-2xl font-bold leading-none mb-3">Reserve your username.</h2>
      <p class="mb-10">Drop your email here and you’ll be first in line when Yay Work is ready to go. You’ll also get your choice of username. But you can’t have <strong>@pat</strong>.</p>
      <form method="post" :action="'https://sendfox.com/form/' + sendfox_user_id + '/' + sendfox_form_id " class="sendfox-form" :id="sendfox_form_id" data-async="true" data-recaptcha="false">
        <div class="md:flex items-center mt-3">
          <div><input type="email" placeholder="your@email.com" name="email" required class="border-2 border-black py-3 px-5 w-100 w-full"/></div>
          <div><button type="submit" class="border-2 border-black py-3 px-6 mt-2 md:mt-0 md:ml-2 bg-rose-300 inline-block cursor-pointer hover:bg-teal-300">Go</button></div>
        </div>
        <!-- no botz please -->
        <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="a_password" tabindex="-1" value="" autocomplete="off" /></div>          
        </form>
        <script src="https://sendfox.com/js/form.js"></script>              
    </div>
    <div class="mt-10">
      <h3>In the meantime...</h3>
      <ul class="leading-5 list-disc mt-2 ml-5">
        <li><a href="https://twitter.com/MrPatGriffith" target="_blank" class="text-blue-700 underline hover:text-gray-900">See progress updates on twitter.</a></li>
        <li><a href="https://github.com/yaywork" target="_blank" class="text-blue-700 underline hover:text-gray-900">Contribute on GitHub.</a></li>
        <li><a href="mailto:mister@patgriffith.com" class="text-blue-700 underline hover:text-gray-900">Email Pat</a>.</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    sendfox_user_id() {
      return process.env.SENDFOX_USER_ID
    },
    sendfox_form_id() {
      return process.env.SENDFOX_FORM_ID
    }
  }
}
</script>
