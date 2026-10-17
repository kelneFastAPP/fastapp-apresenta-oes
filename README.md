# Cadin do Brasil × FastApp: apresentação interativa

Apresentação comercial em HTML com 12 slides animados e demonstrações interativas (website, encomendas, painel, stock e redes sociais), feita para uma reunião de vendas com a Cadin do Brasil.

> Toda a identidade da Cadin (logótipo, cores, produtos, preços e fotografias) é **provisória**. Ver `pesquisa-marcas.md` para saber o que foi confirmado e o que falta pedir.

---

## Abrir a apresentação

| Para… | Abrir | Notas |
|---|---|---|
| **Apresentar ou partilhar com o cliente** | `dist/apresentacao-cadin.html` | Um único ficheiro (4,2 MB) com tudo incluído. Funciona offline, com duplo clique. |
| Editar e testar alterações | `index.html` | Também abre com duplo clique, mas precisa das pastas `src/` e `assets/` ao lado. |
| Publicar num site | `dist/index.html` | Cópia do ficheiro autónomo, pronta para alojamento estático. |

Navegadores recomendados: Chrome ou Edge atualizados. Também funciona em Safari e Firefox recentes.

## Navegar

| Tecla | Ação |
|---|---|
| **→**, **Espaço**, Page Down | slide seguinte |
| **←**, Page Up | slide anterior |
| **F** | ecrã inteiro |
| **R** | repetir a animação do slide atual |
| **S** | vista do apresentador, com as notas de cada slide (abre uma janela nova; permita pop-ups) |
| **O** ou Esc | vista geral de todos os slides |
| Home / End | primeiro / último slide |
| **?** | ajuda com todos os atalhos |

A **barra de controlo** (canto inferior direito) aparece quando se move o rato. Os botões, da esquerda para a direita:

- Início
- Anterior
- Contador
- Seguinte
- Repetir animação
- Reiniciar dados das demonstrações
- Ecrã inteiro

A barra dourada no fundo indica o progresso. Em ecrãs táteis, deslize para os lados.

Ao **avançar**, cada slide anima desde o início. Ao **regressar**, o slide aparece no estado final, sem repetir a animação.

## Demonstrações interativas

| Slide | O que se pode fazer |
|---|---|
| 4: Website | **Explorar demonstração** abre o website em ecrã inteiro: filtrar categorias, abrir produtos, escolher quantidades, carrinho, dados de encomenda e confirmação. **Ver no painel da Cadin** salta para o slide 7. **Voltar à apresentação** ou Esc fecha a demonstração. |
| 5: Encomenda | O telemóvel faz o fluxo sozinho. **Experimentar** para fazer à mão; **Reproduzir** para repetir. |
| 6: Redes sociais | **Nova sugestão** troca a legenda; **Aprovar e agendar** coloca a publicação no calendário. |
| 7: Painel | Clicar num cartão de encomenda avança o estado (Recebida → Em preparação → Pronta → Concluída). |
| 8: Stock | **Simular encomenda** consome ingredientes; **Registar entrada** repõe stock e limpa o alerta. |
| 12: Encerramento | **Vamos construir esta experiência?** mostra o contacto da FastApp. |

Os dados são partilhados entre slides: uma encomenda feita no website ou no slide 5 aparece no painel. Quando passa a "Em preparação", consome stock no slide 8.

Os dados vivem só na memória do navegador. **Reiniciar dados** (ou recarregar a página) volta ao início. Nada é enviado, publicado ou cobrado.

## Preparar a reunião

1. Substituir as fotografias pelas da Cadin (ver abaixo) e, quando estiverem todas, pôr `avisoImagemIlustrativa: false` em `src/js/config.js`.
2. Colocar o logótipo oficial da Cadin (`logoCadin` em `config.js`).
3. Confirmar o e-mail da FastApp em `config.js` (`fastapp.email`).
4. Ajustar produtos e preços demonstrativos em `src/js/data.js`, se houver informação real.
5. Correr `npm run build` para atualizar `dist/apresentacao-cadin.html`.
6. Abrir o ficheiro final no computador da reunião, carregar em **F** e percorrer uma vez todos os slides.
7. Antes de começar, **Reiniciar dados** e voltar ao slide 1.
8. Ler `roteiro-comercial.md`.

## Personalizar

### Fotografias
Coloque novas fotografias em `assets/photos/` **com o mesmo nome** dos ficheiros atuais, ou altere os caminhos em `src/js/config.js` → `photos`. As dimensões recomendadas estão em `pesquisa-marcas.md`. A fotografia do encerramento (`encerramento.jpg`) deve ser horizontal.

### Logótipo da Cadin
Coloque o ficheiro (SVG ou PNG transparente) em `assets/logos/` e indique o caminho em `config.js`:
```js
logoCadin: 'assets/logos/cadin-logo.svg',
logoCadinClaro: 'assets/logos/cadin-logo-branco.svg', // para fundos escuros (opcional)
```

### Textos dos slides
Os textos estão em `index.html`, um bloco por slide (procure `<!-- === 01 ABERTURA` e seguintes). Cada linha dos títulos está num `<span class="ln">` separado, para a animação linha a linha. Mantenha esta estrutura e linhas curtas. As notas do apresentador estão em `<aside class="notes">`.

### Produtos, preços e dados demonstrativos
Em `src/js/data.js`:
- `produtos`: nome, categoria, preço (em euros), unidade, fotografia, descrição.
- `encomendas`: encomendas iniciais do painel.
- `ingredientes` e `receitas`: stock e consumo por unidade.
- `legendas`: sugestões de legenda do slide 6.

### Cores e tipografia
As cores estão no topo de `src/styles/deck.css` (`:root`). As fontes estão em `assets/fonts/`.

### Contacto da FastApp
Em `config.js` → `fastapp` (site e e-mail).

## Gerar a versão autónoma e testar

É preciso o Node.js. Nesta máquina existe uma versão portátil, que não está no PATH. Numa janela PowerShell, dentro desta pasta:

```powershell
$env:Path = "$env:LOCALAPPDATA\Programs\node-v24.21.0-win-x64;$env:Path"
npm install            # só da primeira vez
npm run build          # gera dist/apresentacao-cadin.html e dist/index.html
npm run qa             # percorre os 12 slides: consola, imagens, fontes, texto cortado
npm run qa:1366        # o mesmo em 1366 × 768
npm test               # testa navegação e todas as demonstrações (34 verificações)
npm run test:dist      # o mesmo sobre o ficheiro autónomo
npm run storyboard     # regenera storyboard/ (capturas, fotogramas, demonstrações)
```

Os testes usam o Playwright com o Google Chrome instalado no computador.

## Protótipos: o que ainda não existe

Tudo o que aparece nas interfaces é uma **demonstração conceptual**, sem servidor nem integrações reais:

- Website e encomendas online: protótipo navegável; não envia encomendas nem processa pagamentos.
- Integração com WhatsApp, pagamentos e notificações: apenas mencionadas como possibilidades a definir.
- Publicação automática nas redes sociais: depende das APIs, permissões e políticas da Meta; o fluxo mostrado inclui aprovação humana.
- Painel de encomendas: dados fictícios em memória.
- Stock com baixa automática: depende da configuração das receitas e regras de produção da Cadin.
- Legendas com IA: textos pré-escritos para a demonstração.

Âmbito, prazos e investimento são definidos numa proposta comercial.

## Estrutura

```
apresentacao-cadin-fastapp/
├── index.html               apresentação (código-fonte)
├── dist/
│   ├── apresentacao-cadin.html   versão autónoma para partilhar
│   └── index.html                cópia para alojamento web
├── src/
│   ├── js/   config.js (editável), data.js (dados demo), store.js (estado partilhado),
│   │         site.js (website), apps.js (fluxo, painel, stock), scenes.js (animações GSAP),
│   │         icons.js (ícones, logótipos, azulejo), main.js (Reveal.js e controlos)
│   └── styles/  deck.css (identidade e slides), apps.css (interfaces), ui.css (controlos)
├── assets/
│   ├── photos/   fotografias (ilustrativas, a substituir)
│   ├── logos/    símbolo FastApp oficial (SVG)
│   ├── fonts/    Bricolage Grotesque, Inter, Space Grotesk (+ licenças)
│   └── vendor/   Reveal.js, GSAP (Flip, MotionPath)
├── storyboard/   capturas dos slides, fotogramas das animações, demonstrações, index.html
├── tools/        build, testes, storyboard, descarga de fotografias
├── pesquisa-marcas.md       fontes, identidade e limitações
└── roteiro-comercial.md     narrativa e guião da reunião
```

## Créditos e licenças

- [Reveal.js](https://revealjs.com) 5.2.1, licença MIT.
- [GSAP](https://gsap.com) 3.13.0 com Flip e MotionPathPlugin, licença GSAP Standard (gratuita, incluindo uso comercial).
- Fontes Bricolage Grotesque, Inter e Space Grotesk: SIL Open Font License 1.1 (ficheiros de licença em `assets/fonts/`).
- Fotografias: [Unsplash License](https://unsplash.com/license); autores listados em `pesquisa-marcas.md`.
- Símbolo FastApp: ficheiros oficiais fornecidos pela FastApp.

## Limitações conhecidas

- Num telemóvel na vertical, a apresentação aparece reduzida, com um aviso para rodar o ecrã. O website demonstrativo, esse, adapta-se ao telemóvel.
- A vista do apresentador (**S**) precisa que o navegador permita janelas pop-up.
- O ficheiro autónomo tem 4,2 MB por incluir fotografias e fontes. Ao substituir fotografias, prefira JPEG com cerca de 1500 px no lado maior, para manter o tamanho razoável.
