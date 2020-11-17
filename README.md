# Instalação
``npm install ntlapi.js``

# Iniciar
```js
const NTLAPI = require("ntlapi.js");
const ntl = new NTLAPI("sua-key", client)
```
<br>

# Propiedades
```js
/* Para postar os seus stats: (guilds, users) */
ntl.postStats()

/* Para atualizar os seus stats: (guilds, users) */
ntl.updateStats()
```
<br>

# Parametros
| Params        | Type     |
| ------------- | :-------:|
| warn          | `bool`   |
| refresh_time  | `number` |

<br></br>

# Exemplo

```js
/* PostStats */
ntl.postStats({ warn: false });

 /* true (retorna logs da api) false (retorna nada)*/

ntl.updateStats({ refresh_time: 60000, warn: false });

/* refresh_time é um intervalo de tempo em que á api atualiza seus stats (o parametro é o tempo em ms) */

```

Qualquer duvida ou erro, entrar em contato com á nossa equipe pelo [Discord](https://discord.gg/amYQNpTRaw)
