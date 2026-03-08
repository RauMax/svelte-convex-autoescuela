<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import * as Card from "$lib/components/ui/card";
  import { Switch } from "$lib/components/ui/switch";
  import { Badge } from "$lib/components/ui/badge";
  import { Check } from "@lucide/svelte";

  let isAnnual = $state(false);

  interface Plan {
    name: string;
    desc: string;
    price: number;
    features: string[];
    popular: boolean;
  }

  const plans: Plan[] = [
    {
      name: "Básico",
      desc: "Perfecto para autoescuelas que están empezando.",
      price: 49,
      features: [
        "Hasta 50 alumnos",
        "Gestión de clases",
        "Soporte por email",
        "App móvil básica",
      ],
      popular: false,
    },
    {
      name: "Profesional",
      desc: "Nuestra opción más popular para el crecimiento.",
      price: 99,
      features: [
        "Alumnos ilimitados",
        "Facturación automática",
        "Soporte prioritario 24/7",
        "Analíticas avanzadas",
        "Personalización de marca",
      ],
      popular: true,
    },
    {
      name: "Empresarial",
      desc: "Para grandes cadenas de autoescuelas.",
      price: 199,
      features: [
        "Múltiples sedes",
        "API personalizada",
        "Gestor de cuenta dedicado",
        "Formación presencial",
        "Backup en tiempo real",
      ],
      popular: false,
    },
  ];

  // Lógica de Svelte 5: Estado derivado para el precio anual
  const calculatePrice = (monthlyPrice: number) => {
    if (isAnnual) {
      return Math.floor(monthlyPrice * 0.8); // 20% de descuento
    }
    return monthlyPrice;
  };
</script>

<section id="pricing" class="py-24 bg-white">
  <div class="max-w-7xl mx-auto px-6">
    <div class="text-center max-w-2xl mx-auto mb-16 space-y-6">
      <h2 class="text-4xl md:text-5xl font-black text-slate-900">
        Precios transparentes
      </h2>
      <p class="text-lg text-slate-600">
        Elige el plan que mejor se adapte al tamaño de tu autoescuela. Sin
        comisiones ocultas.
      </p>

      <div class="flex items-center justify-center gap-4 pt-4">
        <span
          id="billing-monthly"
          class="text-sm font-bold {!isAnnual
            ? 'text-slate-900'
            : 'text-slate-400'}">Mensual</span
        >
        <Switch
          checked={isAnnual}
          onCheckedChange={(v: boolean) => (isAnnual = v)}
          aria-labelledby="billing-monthly billing-annual"
        />
        <span
          id="billing-annual"
          class="text-sm font-bold {isAnnual
            ? 'text-slate-900'
            : 'text-slate-400'} flex items-center gap-2"
        >
          Anual
          <Badge
            variant="secondary"
            class="bg-green-100 text-green-700 hover:bg-green-100 border-none"
          >
            AHORRA 20%
          </Badge>
        </span>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      {#each plans as plan (plan.name)}
        <Card.Root
          class="relative flex flex-col {plan.popular
            ? 'border-sky-500 border-2 shadow-2xl scale-105 z-10'
            : 'border-slate-100 shadow-xl'} transition-all duration-300"
        >
          {#if plan.popular}
            <div
              class="absolute top-0 left-1/2 -translate-x-1/2 -translate-y-1/2"
            >
              <Badge
                class="bg-sky-600 px-4 py-1.5 text-sm font-bold uppercase tracking-wider"
                >Más Popular</Badge
              >
            </div>
          {/if}

          <Card.Header class="p-8">
            <Card.Title class="text-2xl font-black text-slate-900 mb-2"
              >{plan.name}</Card.Title
            >
            <Card.Description class="text-slate-500 mb-6"
              >{plan.desc}</Card.Description
            >
            <div
              class="flex items-baseline gap-1"
              aria-label="Precio: {calculatePrice(plan.price)} euros al mes"
            >
              <span
                class="text-5xl font-black text-slate-900"
                aria-hidden="true">€{calculatePrice(plan.price)}</span
              >
              <span class="text-slate-500 font-medium" aria-hidden="true"
                >/mes</span
              >
            </div>
          </Card.Header>

          <Card.Content class="p-8 pt-0 grow">
            <div class="space-y-4">
              {#each plan.features as feature (feature)}
                <div class="flex items-center gap-3">
                  <div
                    class="w-5 h-5 rounded-full bg-green-100 text-green-600 flex items-center justify-center"
                    aria-hidden="true"
                  >
                    <Check size={14} strokeWidth={3} />
                  </div>
                  <span class="text-slate-600 font-medium">{feature}</span>
                </div>
              {/each}
            </div>
          </Card.Content>

          <Card.Footer class="p-8">
            <Button
              class="w-full py-6 text-lg font-bold {plan.popular
                ? 'bg-sky-600 hover:bg-sky-700 shadow-lg shadow-sky-100'
                : 'bg-slate-900 hover:bg-slate-800'}"
              aria-label="Seleccionar plan {plan.name}"
              href="/register?plan={plan.name.toLowerCase()}"
            >
              Seleccionar Plan
            </Button>
          </Card.Footer>
        </Card.Root>
      {/each}
    </div>
  </div>
</section>
