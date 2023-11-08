<script lang="ts">
   import 'metro4/build/css/metro-all.min.css';
	import { type Periodo } from './types/tipos.ts';
  import { afterUpdate, onMount } from "svelte";
  let periodos:Periodo[]=[];

  onMount(async ()=>{
    const response=await fetch("https://app.iedeoccidente.com/getPeriodos.php");
    periodos=[...(await response.json()).filter((periodo:Periodo)=>!periodo.periodo.includes("CINCO")&&!periodo.periodo.includes("MINIMAS"))];
    console.log(periodos)
  });

  afterUpdate(async ()=>{
  
  });

  const traduce=(node:HTMLSelectElement)=>{
  }

 const change=(e:any)=>{
  console.log(e.target.value)
 }

 
</script>
<div class="p-7-sm">
<label for="periodonotas">Período
    <span class="spinner-border spinner-border-sm spperiodo d-none" role="status">
        <span class="visually-hidden">Loading...</span>
    </span>
</label>

<!-- <select id="periodos" on:change={change} use:traduce name="periodo" data-role="select"  class="" tabindex="-1">
  <option value=""></option>
  {#each periodos as periodo(periodo)}
     
     <option value="{periodo.periodo}">{periodo.periodo}</option>
  {/each}
</select> -->
</div>