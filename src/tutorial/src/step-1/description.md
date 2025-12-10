# Començant {#getting-started}

Benvingut al tutorial de Vue!

L’objectiu d’aquest tutorial és donar-te ràpidament una experiència de com és treballar amb Vue, directament al navegador. No pretén ser exhaustiu, i no cal entendre-ho tot abans de continuar. Tanmateix, un cop l’hagis completat, assegura’t de llegir també la <a target="_blank" href="/guide/introduction.html">Guia</a>, que cobreix cada tema amb més detall.

## Prerequisits {#prerequisites}

El tutorial assumeix coneixements bàsics de HTML, CSS i JavaScript. Si ets completament nou en desenvolupament front-end, potser no és la millor idea començar directament amb un framework com a primer pas: aprèn primer els conceptes bàsics i després torna-hi! Tenir experiència prèvia amb altres frameworks ajuda, però no és obligatori.

## Com utilitzar aquest tutorial {#how-to-use-this-tutorial}

Pots editar el codi <span class="wide">a la dreta</span><span class="narrow">a sota</span> i veure el resultat actualitzar-se instantàniament. Cada pas introduirà una funcionalitat principal de Vue, i s’espera que completis el codi perquè la demo funcioni. Si et quedes encallat, disposes d’un botó “Mostra’m!” que revela el codi funcionant. Intenta no dependre’n massa: aprendràs més ràpid descobrint-ho per tu mateix.

Si ets un desenvolupador experimentat provinent de Vue 2 o d’altres frameworks, hi ha algunes opcions que pots ajustar per treure el màxim profit d’aquest tutorial. Si ets principiant, es recomana utilitzar els valors per defecte.

<details>
<summary>Detalls de la configuració del tutorial</summary>

- Vue ofereix dos estils d’API: Options API i Composition API. Aquest tutorial està dissenyat per funcionar amb ambdós; pots triar l’estil que prefereixis utilitzant els interruptors **API Preference** a la part superior. <a target="_blank" href="/guide/introduction.html#api-styles">Més informació sobre estils d’API</a>.

- També pots canviar entre el mode SFC o el mode HTML. El primer mostrarà exemples de codi en format <a target="_blank" href="/guide/introduction.html#single-file-components">Single-File Component</a> (SFC), que és el que la majoria de desenvolupadors utilitza quan treballa amb Vue amb un pas de compilació. El mode HTML mostra l’ús sense pas de compilació.

<div class="html">

:::tip
Si estàs a punt d’utilitzar el mode HTML sense pas de compilació a les teves pròpies aplicacions, assegura’t de canviar les importacions a:

```js
import { ... } from 'vue/dist/vue.esm-bundler.js'
```

dins dels teus scripts o configura l’eina de compilació per resoldre vue adequadament. Exemple de configuració per [Vite](https://vitejs.dev/):

```js [vite.config.js]
export default {
  resolve: {
    alias: {
      vue: 'vue/dist/vue.esm-bundler.js'
    }
  }
}
```

Consulta la [secció corresponent a la Guia d’eines](/guide/scaling-up/tooling.html#note-on-in-browser-template-compilation) per a més informació.
:::

</div>

</details>

Preparat? Fes clic a “Següent” per començar.
