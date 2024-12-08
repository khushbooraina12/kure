<script>
  import { Link } from "svelte-routing";

  let email = "";
  let username = "";
  let password = "";
  let isSignUp = true;

  function handleSubmit() {
    console.log(isSignUp ? "Sign Up" : "Sign In", { email, username, password });
  }

  function toggleForm() {
    isSignUp = !isSignUp;
  }
</script>

<div class="max-w-4xl mx-auto py-8">
  <section id="auth" class="mb-16">
    <h1 class="text-4xl font-bold mb-8">Welcome,</h1>
    <form on:submit|preventDefault={handleSubmit} class="max-w-md mx-auto space-y-4">
      <h2 class="text-2xl font-semibold mb-4">{isSignUp ? 'Sign Up' : 'Sign In'}</h2>
      <input type="email" bind:value={email} placeholder="Email" required class="w-full px-3 py-2 border rounded" />
      {#if isSignUp}
        <input type="text" bind:value={username} placeholder="Username" required class="w-full px-3 py-2 border rounded" />
      {/if}
      <input type="password" bind:value={password} placeholder="Password" required class="w-full px-3 py-2 border rounded" />
      <button type="submit" class="w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700 transition-colors">
        {isSignUp ? 'Sign Up' : 'Sign In'}
      </button>
      <p class="text-center">
        {isSignUp ? 'Already have an account?' : "Don't have an account?"}
        <button type="button" on:click={toggleForm} class="text-blue-600 hover:underline ml-1">
          {isSignUp ? 'Sign In' : 'Sign Up'}
        </button>
      </p>
    </form>
  </section>

  <section id="services" class="mb-16">
    <h2 class="text-3xl font-semibold mb-4">What we do? (Services)</h2>
    <p class="mb-4">
      We help students assess their academic level by conducting personalized tests. After evaluating their performance, we provide a detailed roadmap and review to highlight their strengths and areas for improvement.
    </p>
    <p>
      Along with this, we offer tailored study materials to help them enhance their skills and achieve their full potential. Our goal is to guide students on their learning journey, providing the support they need to grow and succeed academically.
    </p>
  </section>

  <section id="about" class="mb-16">
    <h2 class="text-3xl font-semibold mb-4">Who are we? (About us)</h2>
    <p class="mb-4">
      Hi! We're a team of six students from Usha Mittal Institute of Technology, SNDT Women's University, united by a passion for making learning simple, enjoyable, and accessible. This website is our SIH Hackathon project, designed to create a platform that empowers learners from all backgrounds.
    </p>
    <p>
      Our mission is to make education fun and engaging with an intuitive, user-friendly platform. With our diverse skills in web development, design, and content creation, we're building a space that evolves with your learning needs. Join us on this exciting journey toward accessible, interactive, and enjoyable learning!
    </p>
  </section>

  <section id="contact" class="mb-16">
    <h2 class="text-3xl font-semibold mb-4">CONTACT US</h2>
    <form class="space-y-4">
      <input type="text" placeholder="Name" required class="w-full px-3 py-2 border rounded" />
      <input type="email" placeholder="Email" required class="w-full px-3 py-2 border rounded" />
      <textarea placeholder="Message" rows="4" required class="w-full px-3 py-2 border rounded"></textarea>
      <button type="submit" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700 transition-colors">
        Send Message
      </button>
    </form>
  </section>
</div>

