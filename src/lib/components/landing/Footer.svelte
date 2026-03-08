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
</script>

<footer id="contact" class="bg-slate-900 pt-24 pb-12 text-slate-400">
  <div class="max-w-7xl mx-auto px-6">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-16">
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
          <a
            href="/"
            class="p-2 bg-slate-800 rounded-lg hover:bg-sky-600 hover:text-white transition-all"
          >
            <Facebook size={20} />
          </a>
          <a
            href="/"
            class="p-2 bg-slate-800 rounded-lg hover:bg-sky-600 hover:text-white transition-all"
          >
            <Instagram size={20} />
          </a>
          <a
            href="/"
            class="p-2 bg-slate-800 rounded-lg hover:bg-sky-600 hover:text-white transition-all"
          >
            <Twitter size={20} />
          </a>
        </div>
      </div>

      <div>
        <h4 class="text-white font-bold text-lg mb-6">Plataforma</h4>
        <ul class="space-y-4">
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors"
              >Funcionalidades</a
            >
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors">Precios</a>
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors"
              >Testimonios</a
            >
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors"
              >Seguridad</a
            >
          </li>
        </ul>
      </div>

      <div>
        <h4 class="text-white font-bold text-lg mb-6">Compañía</h4>
        <ul class="space-y-4">
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors"
              >Sobre nosotros</a
            >
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors"
              >Nuestro blog</a
            >
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors">Carreras</a
            >
          </li>
          <li>
            <a href="/" class="hover:text-sky-500 transition-colors">Prensa</a>
          </li>
        </ul>
      </div>

      <div class="space-y-6">
        <h4 class="text-white font-bold text-lg mb-6">Contacto</h4>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
          >
            <Mail size={18} />
          </div>
          <p>hola@autoescuelapro.com</p>
        </div>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
          >
            <Phone size={18} />
          </div>
          <p>+34 900 123 456</p>
        </div>
        <div class="flex items-center gap-3">
          <div
            class="w-10 h-10 bg-slate-800 rounded-lg flex items-center justify-center text-sky-500"
          >
            <MapPin size={18} />
          </div>
          <p>Madrid, España</p>
        </div>
      </div>
    </div>

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
