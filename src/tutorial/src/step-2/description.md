# Renderització Declarativa {#declarative-rendering}

<div class="sfc">

El que veus a l’editor és un Vue Single-File Component (SFC). Un SFC és un bloc de codi reutilitzable i autocontingut que encapsula HTML, CSS i JavaScript que pertanyen junts, escrit dins d’un fitxer `.vue`.

</div>

La funcionalitat principal de Vue és la **renderització declarativa**: utilitzant una sintaxi de plantilla que amplia HTML, podem descriure com hauria de veure’s l’HTML segons l’estat de JavaScript. Quan l’estat canvia, l’HTML s’actualitza automàticament.

<div class="composition-api">

L’estat que pot desencadenar actualitzacions quan canvia es considera **reactiu**. Podem declarar estat reactiu utilitzant l’API `reactive()` de Vue. Els objectes creats amb `reactive()` són [Proxies](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy) de JavaScript que funcionen com a objectes normals:

```js
import { reactive } from 'vue'

const counter = reactive({
  count: 0
})

console.log(counter.count) // 0
counter.count++
```

`reactive()` només funciona amb objectes (incloses matrius i tipus incorporats com `Map` i `Set`). `ref()`, en canvi, pot prendre qualsevol tipus de valor i crear un objecte que exposa el valor intern sota la propietat `.value`:

```js
import { ref } from 'vue'

const message = ref('Hello World!')

console.log(message.value) // "Hello World!"
message.value = 'Changed'
```

Els detalls sobre `reactive()` i `ref()` es tracten a la <a target="_blank" href="/guide/essentials/reactivity-fundamentals.html">Guia - Fonaments de la reactivitat</a>.

<div class="sfc">

L’estat reactiu declarat dins del bloc `<script setup>` del component es pot utilitzar directament a la plantilla. Així és com podem renderitzar text dinàmic basat en el valor de l’objecte `counter` i el `message` utilitzant la sintaxi de mustaches:
</div>

<div class="html">

L’objecte que es passa a `createApp()` és un component de Vue. L’estat d’un component s’ha de declarar dins de la funció `setup()` i retornar-lo mitjançant un objecte:

```js{2,5}
setup() {
  const counter = reactive({ count: 0 })
  const message = ref('Hello World!')
  return {
    counter,
    message
  }
}
```

Les propietats de l’objecte retornat estaran disponibles a la plantilla. Així és com podem renderitzar text dinàmic basat en el valor de `message`, utilitzant la sintaxi de mustaches:

</div>

```vue-html
<h1>{{ message }}</h1>
<p>Count is: {{ counter.count }}</p>
```

Fixeu-vos que no cal utilitzar `.value` quan accedim al ref `message` a les plantilles: es desempaqueta automàticament per a un ús més concís.

</div>

<div class="options-api">

L’estat que pot desencadenar actualitzacions quan canvia es considera **reactiu**. A Vue, l’estat reactiu es manté dins dels components. <span class="html">En el codi d’exemple, l’objecte que es passa a `createApp()` és un component.</span>

Podem declarar estat reactiu utilitzant l’opció `data` del component, que ha de ser una funció que retorni un objecte:

<div class="sfc">

```js{3-5}
export default {
  data() {
    return {
      message: 'Hello World!'
    }
  }
}
```

</div>
<div class="html">

```js{3-5}
createApp({
  data() {
    return {
      message: 'Hello World!'
    }
  }
})
```

</div>

La propietat `message` estarà disponible a la plantilla. Així és com podem renderitzar text dinàmic basat en el valor de `message`, utilitzant la sintaxi de mustaches:

```vue-html
<h1>{{ message }}</h1>
```

</div>

El contingut dins de les mustaches no es limita només a identificadors o rutes: podem utilitzar qualsevol expressió vàlida de JavaScript:

```vue-html
<h1>{{ message.split('').reverse().join('') }}</h1>
```

<div class="composition-api">

Ara, prova de crear un estat reactiu tu mateix i utilitza’l per renderitzar text dinàmic dins del `<h1>` a la plantilla.

</div>

<div class="options-api">

Ara, prova de crear una propietat data tu mateix i utilitza-la com a contingut de text per al `<h1>` a la plantilla.

</div>
