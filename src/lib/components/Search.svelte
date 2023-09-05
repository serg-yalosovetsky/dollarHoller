<script>
	import Search from "$lib/components/Icon/Search.svelte";
</script>

<div class="relative flex items-baseline">   
    <div class="mr-2 text-pastelPurple "><Search/></div> 
    <input  type="text" placeholder="Search by keyword" 
            class="w-72 border-b-2 border-dashed border-b-pastelPurple bg-transparent font-saansSerif text-xl text-black outline-none focus:border-b-lavenderIndigo focus:border-solid" 
            />
    <button class="font-sansSerif text-xl font-black text-pastelPurple">Search</button>


</div>