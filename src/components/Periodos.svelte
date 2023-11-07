<script>
  import { afterUpdate, onMount } from "svelte";

  onMount(()=>{
    console.log("...")
   
  });

  afterUpdate(()=>{
    console.log("...")
  });

  const traduce=(node)=>{
   let search=document.querySelector('input[placeholder="Search..."]');
   search.setAttribute("placeholder", "Buscar");
    
  }
</script>
<div class="p-7-sm">
<label for="periodonotas">Período
    <span class="spinner-border spinner-border-sm spperiodo d-none" role="status">
        <span class="visually-hidden">Loading...</span>
    </span>
</label>
<select use:traduce name="periodo" data-role="select" id="periodonotas" class="" tabindex="-1">

</select>
</div>