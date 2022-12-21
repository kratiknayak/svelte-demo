<div class="carousel">
	<div class="slides" bind:this={siema}>
		<slot></slot>
	</div>
	
    {#if dots}
      <ul class="indicator-dot">
        {#each {length: totalDots} as _, i}
          <li on:click={() => go(i*currentPerPage)} class={isDotActive(currentIndex, i) ? "active" : ""} on:keypress={()=>{}}></li>
        {/each}
      </ul>
    {/if}
</div>

<style>
  .indicator-dot{
    justify-content: right;
  }
	.carousel {
		position: relative;
		width: 100%;
		justify-content: center;
		align-items: center;
	}
	ul {
		list-style-type: none;
		position: absolute;
		display: flex;
		justify-content: center;
		width: 100%;
		margin-top: -30px;
		padding: 0;
	}
	ul li {
		margin: 6px;
		border-radius: 100%;
		background-color: rgba(255,255,255,0.5);
		height: 8px;
		width: 8px;
	}
	ul li:hover {
		background-color: rgba(255,255,255,0.85);
	}
	ul li.active {
		background-color: rgba(255,255,255,1);
	}
</style>

<script>
	import Siema from 'siema'
	import { onMount, createEventDispatcher } from 'svelte'
	
	export let perPage = 1
	export let loop = true
	export let autoplay = 0
	export let duration = 200
	export let easing = 'ease-out'
	export let startIndex = 0
	export let draggable = true
	export let multipleDrag = true	
	export let dots = true	
	export let threshold = 20
	export let rtl = false
	let currentIndex = startIndex;
	
	let siema
	let controller
	let timer
	const dispatch = createEventDispatcher()
	
	$: images = controller ? controller.innerElements : []
	$: currentPerPage = controller ? controller.perPage : perPage
	$: totalDots = controller ? Math.ceil(controller.innerElements.length / currentPerPage) : []
	


	onMount(() => {
		controller = new Siema({
			selector: siema,
			perPage: typeof perPage === 'object' ? perPage : Number(perPage),
			loop,
  			duration,
  			easing,
  			startIndex,
  			draggable,
 			  multipleDrag,
  			threshold,
  			rtl,
			  onChange: handleChange
		})
		if(autoplay) {
			timer = setInterval(right, autoplay);
		}
		return () => {
			autoplay && clearInterval(timer)
			controller.destroy()
		}
	})
	
	export function isDotActive (currentIndex, dotIndex) {
        if (currentIndex < 0) currentIndex = images.length + currentIndex;
        return currentIndex >= dotIndex*currentPerPage && currentIndex < (dotIndex*currentPerPage)+currentPerPage
    }
	
	export function left () {
		controller.prev()
	}
	
	export function right () {
		controller.next()
	}
	
	export function go (index) {
		controller.goTo(index)
	}
	
	export function pause() {
		clearInterval(timer);
	}
	
	
	
	function handleChange (event) {
		currentIndex = controller.currentSlide
		dispatch('change', {
			currentSlide: controller.currentSlide,
			slideCount: controller.innerElements.length
		} )
	}
	
	
</script>