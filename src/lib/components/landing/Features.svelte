<script lang="ts">
  import {
    Users,
    Calendar,
    CreditCard,
    ShieldCheck,
    Smartphone,
    BarChart3,
    type Icon,
  } from "@lucide/svelte";
  import * as Card from "$lib/components/ui/card";
  import type { Component } from "svelte";

  // Definimos la estructura de una funcionalidad para mayor seguridad
  interface Feature {
    title: string;
    desc: string;
    icon: Component<any>;
    color: string;
  }

  const features: Feature[] = [
    {
      title: "Gestión de Alumnos",
      desc: "Expedientes digitales, seguimiento de progreso y documentación organizada.",
      icon: Users,
      color: "bg-blue-50 text-blue-600",
    },
    {
      title: "Calendario Inteligente",
      desc: "Agenda clases prácticas fácilmente y evita solapamientos de instructores.",
      icon: Calendar,
      color: "bg-purple-50 text-purple-600",
    },
    {
      title: "Pagos y Facturación",
      desc: "Control total de cobros, facturas automáticas y estados de cuenta.",
      icon: CreditCard,
      color: "bg-green-50 text-green-600",
    },
    {
      title: "Seguridad de Datos",
      desc: "Toda tu información protegida y con copias de seguridad automáticas.",
      icon: ShieldCheck,
      color: "bg-red-50 text-red-600",
    },
    {
      title: "Multiplataforma",
      desc: "Accede desde tu móvil, tablet o computadora en cualquier momento.",
      icon: Smartphone,
      color: "bg-orange-50 text-orange-600",
    },
    {
      title: "Estadísticas Reales",
      desc: "Visualiza el rendimiento de tu autoescuela con gráficos intuitivos.",
      icon: BarChart3,
      color: "bg-sky-50 text-sky-600",
    },
  ];
</script>

<section id="features" class="py-24 bg-slate-50/50">
  <div class="max-w-7xl mx-auto px-6">
    <div class="text-center max-w-3xl mx-auto mb-16 space-y-4">
      <h2 class="text-sky-600 font-bold tracking-wider uppercase text-sm">
        Funcionalidades
      </h2>
      <h3 class="text-4xl md:text-5xl font-black text-slate-900">
        Todo lo que necesitas para <br />
        <span class="text-slate-500 font-medium">hacer crecer tu negocio.</span>
      </h3>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each features as feature (feature.title)}
        <Card.Root
          class="group border-none shadow-md hover:shadow-xl transition-all duration-300 hover:-translate-y-1 bg-white overflow-hidden"
        >
          <Card.Header class="p-8">
            <div
              class="w-14 h-14 rounded-2xl {feature.color} flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300"
              aria-hidden="true"
            >
              <feature.icon size={28} />
            </div>
            <Card.Title
              class="text-xl font-bold mb-3 text-slate-900 group-hover:text-sky-600 transition-colors"
            >
              {feature.title}
            </Card.Title>
            <Card.Description class="text-base text-slate-500 leading-relaxed">
              {feature.desc}
            </Card.Description>
          </Card.Header>
          <div
            class="h-1 w-0 bg-sky-600 group-hover:w-full transition-all duration-500"
          ></div>
        </Card.Root>
      {/each}
    </div>
  </div>
</section>
