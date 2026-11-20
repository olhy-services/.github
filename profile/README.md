<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/olhy-services/.github/raw/main/profile/assets/banner-dark.svg">
  <img alt="Olhy open source: olhy-redis-view, gps-simulator e device-lab" src="https://github.com/olhy-services/.github/raw/main/profile/assets/banner-light.svg" width="100%">
</picture>

<p>
  <a href="https://olhy.com.br"><img alt="olhy.com.br" src="https://img.shields.io/badge/site-olhy.com.br-ed261c?style=flat-square"></a>
  <a href="mailto:contato@olhy.com.br"><img alt="contato@olhy.com.br" src="https://img.shields.io/badge/contato-contato%40olhy.com.br-18181b?style=flat-square"></a>
  <img alt="Licença MIT" src="https://img.shields.io/badge/licen%C3%A7a-MIT-18181b?style=flat-square">
  <img alt="Feito no Brasil" src="https://img.shields.io/badge/feito%20no-Brasil-18181b?style=flat-square">
</p>

A **Olhy** é uma empresa brasileira de tecnologia. Nosso produto é o **Olhy Food**:
cardápio digital, pedidos, delivery, PDV, cozinha e app do entregador para
restaurantes.

Para construir tudo isso a gente precisou de ferramentas que não existiam do jeito que
queríamos. Elas estão aqui, abertas. Todas seguem as mesmas regras:

- **Rodam no seu computador.** Escutam só em `127.0.0.1`; nada vai para servidor nosso.
- **Não instalam nada no aparelho nem no banco.** Usam o que já existe: `adb`, `xcrun`,
  protocolo do Redis.
- **TypeScript estrito**, sem `any`, entrada validada com Zod, licença MIT.

---

## olhy-redis-view

**Ver, gerenciar e consultar bancos Redis pelo navegador.** Um comando abre a interface;
standalone, Sentinel, Cluster, TLS e túnel SSH. Funciona também com Valkey, KeyDB e
Dragonfly.

<p>
  <a href="https://github.com/olhy-services/olhy-redis-view"><img alt="Repositório" src="https://img.shields.io/badge/repo-olhy--redis--view-18181b?style=flat-square&logo=github"></a>
  <img alt="Estrelas" src="https://img.shields.io/github/stars/olhy-services/olhy-redis-view?style=flat-square&label=estrelas&color=18181b">
  <img alt="Último commit" src="https://img.shields.io/github/last-commit/olhy-services/olhy-redis-view?style=flat-square&label=atualizado&color=18181b">
</p>

<img alt="olhy-redis-view em uso: árvore de chaves, Workbench, análise de memória e gráficos do servidor" src="https://github.com/olhy-services/.github/raw/main/profile/assets/redis-tour.gif" width="100%">

<table>
  <tr>
    <td width="50%" valign="top">
      <img alt="Árvore de chaves com um hash aberto" src="https://github.com/olhy-services/.github/raw/main/profile/assets/redis-keys.png">
      <b>Chaves.</b> Árvore pelo separador, <code>SCAN</code> em páginas (nunca <code>KEYS</code>), editor para string, hash, list, set, zset, stream e RedisJSON. Valores como texto, JSON, hex, gzip ou MessagePack, sem corromper binário.
    </td>
    <td width="50%" valign="top">
      <img alt="Workbench com autocomplete" src="https://github.com/olhy-services/.github/raw/main/profile/assets/redis-workbench.png">
      <b>Workbench.</b> Sintaxe do <code>redis-cli</code>, autocomplete com os comandos do próprio servidor (inclusive módulos), <code>Ctrl+Enter</code> roda o trecho selecionado, histórico por conexão.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img alt="Painel do servidor com gráficos" src="https://github.com/olhy-services/.github/raw/main/profile/assets/redis-server.png">
      <b>Servidor.</b> Comandos/s, memória, clientes, rede e taxa de acerto ao vivo. Clientes conectados, slowlog, <code>CONFIG</code> e <code>INFO</code> completo.
    </td>
    <td width="50%" valign="top">
      <img alt="Análise de memória por tipo, TTL e prefixo" src="https://github.com/olhy-services/.github/raw/main/profile/assets/redis-analysis.png">
      <b>Análise de memória.</b> O que ocupa espaço por tipo, por faixa de TTL, por prefixo e as maiores chaves. Um clique abre as chaves daquele prefixo.
    </td>
  </tr>
</table>

Também tem Pub/Sub, `MONITOR`, apagar por padrão com simulação antes, exportar e
importar (`DUMP`/`RESTORE`). Em conexão de **produção**, ação destrutiva pede o nome da
conexão; em **somente leitura**, o servidor bloqueia qualquer escrita, até no Workbench.

```bash
git clone https://github.com/olhy-services/olhy-redis-view.git && cd olhy-redis-view
pnpm install && pnpm build
pnpm start -- redis://127.0.0.1:6379
```

---

## gps-simulator

**GPS em movimento no Android e no simulador iOS.** Marque o ponto A, o B e paradas no
mapa: o aparelho "anda" pela rota **pelas ruas**, na velocidade que você escolher, como
numa entrega de verdade. Todo app do aparelho recebe a posição: o seu app em
desenvolvimento, mapas, app de entrega.

<p>
  <a href="https://github.com/olhy-services/gps-simulator"><img alt="Repositório" src="https://img.shields.io/badge/repo-gps--simulator-18181b?style=flat-square&logo=github"></a>
  <img alt="Estrelas" src="https://img.shields.io/github/stars/olhy-services/gps-simulator?style=flat-square&label=estrelas&color=18181b">
  <img alt="Último commit" src="https://img.shields.io/github/last-commit/olhy-services/gps-simulator?style=flat-square&label=atualizado&color=18181b">
</p>

<img alt="gps-simulator com uma rota de entrega traçada pelas ruas" src="https://github.com/olhy-services/.github/raw/main/profile/assets/gps.png" width="100%">

| | |
|---|---|
| **Aparelhos** | Android 12+ por USB ou Wi-Fi (sem app instalado), emulador Android, simulador iOS no macOS. |
| **Rota** | Busca de endereço, pontos arrastáveis, tempo de espera em cada parada, ida e volta. Rotas reais pelo OSRM. |
| **Movimento** | Velocidade, acelerar o tempo até 20×, ida e volta, precisão e ruído do GPS, deixar parado num ponto com o botão direito. O relógio roda no servidor: fechar a aba não para a simulação. |
| **Cenários** | Salvos em JSON na pasta `scenarios/` e executáveis pela linha de comando (`pnpm sim run cenario.json`), prontos para testes de ponta a ponta. |

```bash
git clone https://github.com/olhy-services/gps-simulator.git && cd gps-simulator
pnpm install && pnpm dev
```

---

## device-lab

**Um Android espelhado no navegador, com o DevTools do aparelho ao lado.** Use o
celular com mouse e teclado e veja, em tempo real, o que ele está fazendo, para
**qualquer app**, não só o seu. Funciona por USB ou Wi-Fi, sem instalar nada no
aparelho.

<p>
  <a href="https://github.com/olhy-services/device-lab"><img alt="Repositório" src="https://img.shields.io/badge/repo-device--lab-18181b?style=flat-square&logo=github"></a>
  <img alt="Estrelas" src="https://img.shields.io/github/stars/olhy-services/device-lab?style=flat-square&label=estrelas&color=18181b">
  <img alt="Último commit" src="https://img.shields.io/github/last-commit/olhy-services/device-lab?style=flat-square&label=atualizado&color=18181b">
</p>

O scrcpy espelha a tela, o Android Studio mostra o profiler, o HTTP Toolkit captura
requisições e o `adb logcat` mostra o log, cada um numa janela. O device-lab junta
tudo numa página:

| Aba | O que mostra |
|---|---|
| **Tela** | Espelho com toque, rolagem, teclado, área de transferência nos dois sentidos, captura em PNG e gravação. |
| **Visão geral** | CPU por núcleo, RAM, rede, temperaturas e bateria (corrente, tensão, saúde). |
| **Desempenho** | Quadros/s do app aberto, % de quadros lentos, p90 do tempo de quadro, CPU e memória. |
| **Rede** | Conexões de todos os apps (dono, servidor, porta) e inspetor de requisições HTTP/HTTPS com "copiar como cURL". |
| **Logcat** | Ao vivo, por nível, com busca e filtro "só o app na tela". |
| **Apps, Arquivos, Processos** | Instalar APK arrastando, navegar pastas (inclusive a privada de apps de debug), encerrar processos. |

```mermaid
flowchart LR
  B["Navegador<br/>espelho + DevTools"] <-- "WebSocket<br/>vídeo H.264 · toques" --> S["device-lab<br/>Node local"]
  S <-- "adb · scrcpy-server" --> A["Android<br/>USB ou Wi-Fi"]
  A -. "proxy HTTP/HTTPS<br/>(adb reverse)" .-> S
```

```bash
git clone https://github.com/olhy-services/device-lab.git && cd device-lab
pnpm install && pnpm dev
```

---

## Feito com

<p>
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178c6?style=flat-square&logo=typescript&logoColor=white">
  <img alt="Node.js 22" src="https://img.shields.io/badge/Node.js_22-339933?style=flat-square&logo=nodedotjs&logoColor=white">
  <img alt="React" src="https://img.shields.io/badge/React-149eca?style=flat-square&logo=react&logoColor=white">
  <img alt="Vite" src="https://img.shields.io/badge/Vite-646cff?style=flat-square&logo=vite&logoColor=white">
  <img alt="Zod" src="https://img.shields.io/badge/Zod-3068b7?style=flat-square&logo=zod&logoColor=white">
  <img alt="MapLibre" src="https://img.shields.io/badge/MapLibre-396cb2?style=flat-square&logo=maplibre&logoColor=white">
  <img alt="Redis" src="https://img.shields.io/badge/Redis-ff4438?style=flat-square&logo=redis&logoColor=white">
  <img alt="Android" src="https://img.shields.io/badge/Android-34a853?style=flat-square&logo=android&logoColor=white">
</p>

## Contribuir

Issues e pull requests são bem-vindos. Cada repositório tem um `CONTRIBUTING.md` com
como rodar e testar, e um `SECURITY.md`: falha de segurança vai pelo reporte privado
do GitHub, não em issue pública.

<sub>Olhy Tecnologia · <a href="https://olhy.com.br">olhy.com.br</a></sub>
