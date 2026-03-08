<script lang="ts">
  import { Menu, X } from "@lucide/svelte";
  import { Button } from "$lib/components/ui/button";
  import Separator from "$lib/components/ui/separator/separator.svelte";

  let isOpen = $state(false);

  interface NavLink {
    name: string;
    href: string;
  }

  const navLinks: NavLink[] = [
    { name: "Nosotros", href: "#about" },
    { name: "Funcionalidades", href: "#features" },
    { name: "Precios", href: "#pricing" },
    { name: "Contacto", href: "#contact" },
  ];
</script>

<nav
  class="sticky top-0 z-50 w-full bg-white/80 backdrop-blur-md border-b border-slate-100"
>
  <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
    <!-- Logo -->
    <a
      href="/"
      class="flex items-center gap-2 group"
      aria-label="AutoEscuelaPro - Ir al inicio"
    >
      <div
        class="w-10 h-10 bg-sky-600 rounded-xl flex items-center justify-center text-white font-black text-xl shadow-lg shadow-sky-200 group-hover:scale-105 transition-transform"
        aria-hidden="true"
      >
        A
      </div>
      <span class="text-xl font-bold tracking-tight text-slate-900">
        AutoEscuela<span class="text-sky-600">Pro</span>
      </span>
    </a>

    <!-- Desktop Navigation -->
    <div class="hidden md:flex items-center gap-1">
      {#each navLinks as link (link.name)}
        <a
          href={link.href}
          class="px-4 py-2 text-sm font-medium text-slate-600 hover:text-sky-600 transition-colors rounded-md hover:bg-slate-50"
        >
          {link.name}
        </a>
      {/each}
      <div class="h-6 w-px bg-slate-200 mx-4" aria-hidden="true"></div>
      <Button variant="ghost" href="/login" class="text-slate-600"
        >Entrar</Button
      >
      <Button
        href="/register"
        class="bg-sky-600 hover:bg-sky-700 shadow-lg shadow-sky-100"
      >
        Prueba Gratis
      </Button>
    </div>

    <!-- Mobile Button -->
    <button
      class="md:hidden p-2 text-slate-600 hover:bg-slate-100 rounded-lg transition-colors"
      onclick={() => (isOpen = !isOpen)}
      aria-label={isOpen ? "Cerrar menú" : "Abrir menú"}
      aria-expanded={isOpen}
    >
      {#if isOpen}
        <X size={24} aria-hidden="true" />
      {:else}
        <Menu size={24} aria-hidden="true" />
      {/if}
    </button>
  </div>

  <!-- Mobile Menu -->
  {#if isOpen}
    <div
      class="md:hidden bg-white border-t border-slate-100 p-6 flex flex-col gap-2 animate-in slide-in-from-top duration-300"
    >
      {#each navLinks as link (link.name)}
        <a
          href={link.href}
          class="px-4 py-3 text-lg font-medium text-slate-600 hover:bg-slate-50 rounded-lg"
          onclick={() => (isOpen = false)}
        >
          {link.name}
        </a>
      {/each}
      <Separator class="my-2" aria-hidden="true" />
      <div class="flex flex-col gap-3">
        <Button variant="outline" href="/login" class="w-full py-6 text-lg"
          >Entrar</Button
        >
        <Button href="/register" class="w-full py-6 text-lg bg-sky-600"
          >Empezar Ahora</Button
        >
      </div>
    </div>
  {/if}
</nav>
