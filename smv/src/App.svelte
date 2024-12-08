<script>
	import { Router, Link, Route } from "svelte-routing";
	import Home from "./routes/Home.svelte";
	import Profile from "./routes/Profile.svelte";
	import Assessments from "./routes/Assessments.svelte";
	import Mitra from "./routes/Mitra.svelte";
	import MyLearnings from "./routes/MyLearnings.svelte";
	import Feedback from "./routes/Feedback.svelte";
  
	export let url = "";
  </script>
  
  <Router {url}>
	<nav class="bg-blue-600 text-white p-4">
	  <div class="container mx-auto flex justify-between items-center">
		<Link to="/" class="text-2xl font-bold">Logo</Link>
		<div class="space-x-4">
		  <a href="#services" class="hover:underline">Services</a>
		  <a href="#contact" class="hover:underline">Contact Us</a>
		  <a href="#about" class="hover:underline">About Us</a>
		</div>
	  </div>
	</nav>
  
	<main class="container mx-auto p-4">
	  <Route path="/" component={Home} />
	  <Route path="/profile" component={Profile} />
	  <Route path="/assessments" component={Assessments} />
	  <Route path="/mitra" component={Mitra} />
	  <Route path="/mylearnings" component={MyLearnings} />
	  <Route path="/feedback" component={Feedback} />
	</main>
  </Router>
  
  