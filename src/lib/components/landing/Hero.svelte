<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import { ArrowRight, Play } from "@lucide/svelte";
</script>

<section
  class="relative pt-20 pb-24 md:pt-32 md:pb-40 overflow-hidden bg-white"
>
  <!-- Background Decorations -->
  <div
    class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full pointer-events-none -z-10"
  >
    <div
      class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-sky-50 rounded-full blur-3xl opacity-60"
    ></div>
    <div
      class="absolute bottom-[10%] right-[-10%] w-[30%] h-[30%] bg-indigo-50 rounded-full blur-3xl opacity-60"
    ></div>
  </div>

  <div
    class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-16 items-center"
  >
    <div class="text-left space-y-8">
      <div
        class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-sky-50 text-sky-700 text-sm font-semibold border border-sky-100"
      >
        <span class="relative flex h-2 w-2">
          <span
            class="animate-ping absolute inline-flex h-full w-full rounded-full bg-sky-400 opacity-75"
          ></span>
          <span class="relative inline-flex rounded-full h-2 w-2 bg-sky-500"
          ></span>
        </span>
        Nuevo: Gestión de Exámenes Automática
      </div>

      <h1
        class="text-5xl md:text-7xl font-black text-slate-900 leading-[1.1] tracking-tight"
      >
        Aprende a conducir <br />
        <span
          class="text-transparent bg-clip-text bg-gradient-to-r from-sky-600 to-indigo-600"
        >
          sin complicaciones.
        </span>
      </h1>

      <p class="text-xl text-slate-600 leading-relaxed max-w-xl">
        La plataforma líder para autoescuelas modernas. Gestiona tus alumnos,
        clases prácticas y pagos en un solo lugar.
        <span class="font-semibold text-slate-900"
          >Ahorra tiempo y dinero desde el primer día.</span
        >
      </p>

      <div class="flex flex-col sm:flex-row items-center gap-4">
        <Button
          size="lg"
          class="w-full sm:w-auto px-8 py-7 text-lg bg-sky-600 hover:bg-sky-700 shadow-xl shadow-sky-200 transition-all hover:-translate-y-1"
        >
          Empezar Ahora Gratis
          <ArrowRight class="ml-2 w-5 h-5" />
        </Button>
        <Button
          size="lg"
          variant="outline"
          class="w-full sm:w-auto px-8 py-7 text-lg border-2 hover:bg-slate-50 transition-all"
        >
          <Play class="mr-2 w-5 h-5 fill-slate-900" />
          Ver Video Demo
        </Button>
      </div>

      <div class="flex items-center gap-4 pt-4">
        <div class="flex -space-x-3">
          {#each Array(4) as _, i}
            <div
              class="w-10 h-10 rounded-full border-2 border-white bg-slate-200 overflow-hidden"
            >
              <img src="https://i.pravatar.cc/100?img={i + 10}" alt="Usuario" />
            </div>
          {/each}
        </div>
        <div class="text-sm text-slate-500">
          <span class="font-bold text-slate-900">+500 autoescuelas</span> ya confían
          en nosotros
        </div>
      </div>
    </div>

    <div class="relative group">
      <div
        class="absolute -inset-4 bg-gradient-to-tr from-sky-500 to-indigo-500 rounded-[2rem] blur-2xl opacity-20 group-hover:opacity-30 transition-opacity"
      ></div>
      <div
        class="relative bg-white rounded-[2rem] border border-slate-200 overflow-hidden shadow-2xl"
      >
        <div
          class="aspect-video bg-slate-900 flex items-center justify-center relative"
        >
          <img
            src="https://images.unsplash.com/photo-1596484552979-3300f43963ba?auto=format&fit=crop&q=80&w=1200"
            alt="Dashboard AutoEscuelaPro"
            class="w-full h-full object-cover opacity-80"
          />
          <div
            class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"
          ></div>
          <button
            class="absolute inset-0 flex items-center justify-center group/btn"
          >
            <div
              class="w-20 h-20 bg-white/20 backdrop-blur-md rounded-full flex items-center justify-center group-hover/btn:scale-110 transition-transform"
            >
              <div
                class="w-16 h-16 bg-white rounded-full flex items-center justify-center shadow-2xl"
              >
                <Play class="w-8 h-8 text-sky-600 fill-sky-600" />
              </div>
            </div>
          </button>
        </div>

        <!-- Floating UI Elements -->
        <div
          class="absolute bottom-6 left-6 right-6 p-4 bg-white/90 backdrop-blur-lg rounded-xl border border-white/20 shadow-lg flex items-center justify-between animate-in fade-in slide-in-from-bottom-4 duration-700"
        >
          <div class="flex items-center gap-3">
            <div
              class="w-10 h-10 bg-green-100 text-green-600 rounded-full flex items-center justify-center font-bold"
            >
              ✓
            </div>
            <div>
              <p class="text-sm font-bold text-slate-900">Examen aprobado</p>
              <p class="text-xs text-slate-500">Alumno: Juan Pérez</p>
            </div>
          </div>
          <div class="text-right">
            <p class="text-sm font-black text-slate-900">95%</p>
            <p class="text-[10px] text-slate-500 font-medium">Tasa de éxito</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
