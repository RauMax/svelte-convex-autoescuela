<script lang="ts">
  import {
    Facebook,
    Instagram,
    Twitter,
    Linkedin,
    Mail,
    MapPin,
    Phone,
  } from "@lucide/svelte";
  import type { Component } from "svelte";

  // Tipado para los enlaces
  interface FooterLink {
    name: string;
    href: string;
  }

  interface FooterGroup {
    title: string;
    links: FooterLink[];
  }

  // Estructura de datos para los grupos de links
  const linkGroups: FooterGroup[] = [
    {
      title: "Plataforma",
      links: [
        { name: "Funcionalidades", href: "/" },
        { name: "Precios", href: "/" },
        { name: "Testimonios", href: "/" },
        { name: "Seguridad", href: "/" },
      ],
    },
    {
      title: "Compañía",
      links: [
        { name: "Sobre nosotros", href: "/" },
        { name: "Nuestro blog", href: "/" },
        { name: "Carreras", href: "/" },
        { name: "Prensa", href: "/" },
      ],
    },
  ];

  // Redes sociales con sus tipos
  interface SocialLink {
    icon: Component<any>;
    href: string;
    label: string;
  }

  const socialLinks: SocialLink[] = [
    { icon: Facebook, href: "/", label: "Ir a Facebook" },
    { icon: Instagram, href: "/", label: "Ir a Instagram" },
    { icon: Twitter, href: "/", label: "Ir a Twitter" },
  ];
</script>

<footer id="contact" class="bg-slate-900 pt-24 pb-12 text-slate-400">
  <div class="max-w-7xl mx-auto px-6">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-16">
      <!-- Columna Branding -->
      <div class="space-y-6">
        <a href="/" class="flex items-center gap-2">
          <div
            class="w-8 h-8 bg-sky-600 rounded-lg flex items-center justify-center text-white font-black"
          >
            A
          </div>
          <span class="text-xl font-bold tracking-tight text-white">
            AutoEscuela<span class="text-sky-600">Pro</span>
          </span>
        </a>
        <p class="leading-relaxed">
          Transformando la gestión de las autoescuelas con tecnología de
          vanguardia y diseño centrado en el usuario.
        </p>
        <div class="flex gap-4">
          {#each socialLinks as social (social.label)}
            <a
              href={social.href}
              class="p-2 bg-slate-800 rounded-lg hover:bg-sky-600 hover:text-white transition-all"
              aria-label={social.label}
            >
              <social.icon size={20} />
            </a>
          {/each}
        </div>
      </div>

      <!-- Columnas de Links Dinámicas -->
      {#each linkGroups as group (group.title)}
        <div>
          <h4 class="text-white font-bold text-lg mb-6">{group.title}</h4>
          <ul class="space-y-4">
            {#each group.links as link (link.name)}
              <li>
                <a
                  href={link.href}
                  class="hover:text-sky-500 transition-colors"
                >
                  {link.name}
                </a>
              </li>
            {/each}
          </ul>
        </div>
      {/each}

      <!-- Columna Contacto con Links Inteligentes -->
      <div class="space-y-6">
        <h4 class="text-white font-bold text-lg mb-6">Contacto</h4>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
            aria-hidden="true"
          >
            <Mail size={18} />
          </div>
          <a
            href="mailto:hola@autoescuelapro.com"
            class="hover:text-sky-500 transition-colors"
          >
            hola@autoescuelapro.com
          </a>
        </div>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
            aria-hidden="true"
          >
            <Phone size={18} />
          </div>
          <a
            href="tel:+34900123456"
            class="hover:text-sky-500 transition-colors"
          >
            +34 900 123 456
          </a>
        </div>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
            aria-hidden="true"
          >
            <MapPin size={18} />
          </div>
          <p>Madrid, España</p>
        </div>
      </div>
    </div>

    <!-- Footer Inferior -->
    <div
      class="pt-12 border-t border-slate-800 flex flex-col md:flex-row justify-between items-center gap-6 text-sm"
    >
      <p>© 2026 AutoEscuelaPro S.L. Todos los derechos reservados.</p>
      <div class="flex gap-8">
        <a href="/" class="hover:text-white transition-colors">Privacidad</a>
        <a href="/" class="hover:text-white transition-colors">Términos</a>
        <a href="/" class="hover:text-white transition-colors">Cookies</a>
      </div>
    </div>
  </div>
</footer>
