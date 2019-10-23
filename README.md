# Temario VueJS

1. ¿Que es VueJS?
2. Vue Object
   ```
   const vue = new Vue({
       el: '#app',
       data: {
           name: 'Adrián'                  // Declaración de las variables
       },
       methods: {
           reverseName: function() {       // Declaración de los métodos
               return this.name.split('').reverse().join('');
           }
       },
       computed: {
           output: function() {            // Variables computadas
               return this.name.split('').reverse().join('');
           }
       },
       watch: {
           name: function(value) {         // Funciones que se ejecutan al cambiar una variable.
               console.log(value)          // La función se debe de llamar igual
           }                               //que la variable que observa.
       }
   });
   ```
3. Vue Directives
   - v-bind
   - v-once
   - v-html
   - v-on
4. Vue Component

   - props
     Son datos que se pasan de un componente padre a uno o más componentes hijos

     su forma más básica se componen por :

   ```
       const vue = new Vue({
           props: {
               text: [String, Number]
           }
       });
   ```

   O, definido de una mejor manera

   ```
   const vue = new Vue({
       props: {
           text: {
               type: String,
               required: true,
               default: 'Cualquier valor'
           }
       }
   });
   ```

   Los objetos necesitan que su valor default sea definido mediante una función

   ```
   const vue = new Vue({
       props: {
           text: {
               type: Object,
               default: function() {
                   return { message: 'Hola a Mundo!' };
               }
           }
       }
   });
   ```

5. Vue Form
6. HTTP Request

# Cli

```
npm install tailwindcss
npm install axios --save

```

# postcss.config.js

```
module.exports = {
    plugins: [require('tailwindcss'), require('autoprefixer')]
};
```

# .prettierrc.js

```
module.exports = {
    singleQuote: true
};
```

# .eslintrc.js

```
module.exports = {
  root: true,
  env: {
    node: true
  },
  extends: ['plugin:vue/essential', '@vue/prettier'],
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'error' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'error' : 'off'
  },
  parserOptions: {
    parser: 'babel-eslint'
  }
};
```

# assets/css/tailwind.css

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

# main.js

```
Vue.prototype.$http = axios;
```
