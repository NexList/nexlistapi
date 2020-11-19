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

/* Para pegar os seus stats: (views, guilds, users, verifield) */
ntl.getStats()
```
<br>

# Parametros
| Params        | Type     |
| ------------- | :-------:|
| warn          | `bool`   |
| refresh_time  | `number` |

<br></br>

# Exemplos

```js
/* PostStats */
ntl.postStats({ warn: false });

/* true (retorna logs da api) false (retorna nada)*/

/* updateStats */
ntl.updateStats({ refresh_time: 60000, warn: false });

/* refresh_time é um intervalo de tempo em que á api atualiza seus stats (o parametro é o tempo em ms) */

/* getStats */
ntl.getStats(client.user.id, (stats) => {
  console.log(stats) //{ views: 0, users: 0, guilds: 0, verifield: bool }
});

/* No getStats você deve passar como o primeiro parametro o id do seu bot, depois você faz uma callback function pegando como parametro um objeto...
Dentro desse objeto ira conter todos os stats do seu bot!
*/
```

# Callbacks

Uma `callback` é uma função, que deve ser executada logo apos todo o conteudo for iniciado...<br><br>
**Obs**: Tudo que estiver dentro da callback sera executada assim que todo conteudo for carregado, ou seja se você utilizar o `postStats` e passar uma callback nele todo conteudo da callback sera executada assim que seus stats foram atualizados!
__ __
Exemplo de como utilizar uma callback em nossa library:

```js
//Com logs
ntl.postStats({ warn: false }, () => {
  console.log("Meus stats foram postados")
});

//Exemplo real:
ntl.updateStats({ refresh_time: 60000, warn: false }, () => {
  const channel = client.channels.cache.get("123125412512512");

  channel.send("Meus stats foram atualizados as: " + Date.now());
});
```

Qualquer duvida ou erro, entrar em contato com á nossa equipe pelo [Discord](https://discord.gg/amYQNpTRaw)
