<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  let count = $state(0);
</script>

<div class="p-8">
  <h1 class="text-2xl font-bold mb-4">Ejercicio 1: Contador Básico</h1>
  <p class="mb-4">El valor es: {count}</p>
  <div class="flex gap-2">
    <Button onclick={() => count++}>Incrementar</Button>
    <Button onclick={() => count--}>Decrementar</Button>
  </div>

  <a href="/" class="block mt-8 text-blue-600 hover:underline">
    ← Volver al inicio (Ejercicio 2)
  </a>
</div>
