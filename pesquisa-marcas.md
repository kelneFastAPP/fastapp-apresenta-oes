# Pesquisa de marcas: Cadin do Brasil e FastApp

Pesquisa feita a 17 de outubro de 2026 para orientar a direção criativa da apresentação.

## Resumo

| | Cadin do Brasil | FastApp |
|---|---|---|
| Logótipo | **Não obtido.** Usado um logótipo tipográfico provisório. | **Confirmado.** Vetor oficial extraído da apresentação institucional. |
| Paleta | **Não confirmada.** Paleta provisória gastronómica. | **Confirmada** (site atual e apresentação institucional). |
| Tipografia | **Não confirmada.** | **Confirmada** no código do site (Space Grotesk, Inter). |
| Produtos | **Não confirmados.** Catálogo demonstrativo com produtos típicos, assinalado como fictício. | Serviços confirmados no site. |
| Fotografias | **Nenhuma fotografia autorizada obtida.** Fotografias ilustrativas de banco de imagens, assinaladas. | Não aplicável. |
| Contacto | **Não confirmado.** | E-mail encontrado no código do site, a confirmar. |

---

## 1. Cadin do Brasil

### Fontes consultadas

| Fonte | Resultado |
|---|---|
| [instagram.com/cadin_do_brasil](https://www.instagram.com/cadin_do_brasil/) | A página pública só devolve o título **"Cadin do Brasil 🇧🇷🇵🇹"**. O Instagram responde com uma página de erro a quem não tem sessão iniciada. **Não foi feita qualquer tentativa de contornar a autenticação** nem foram usados serviços que espelham o Instagram. |
| Pesquisa web: "Cadin do Brasil" salgados doces Portugal | Sem resultados sobre a marca. |
| Pesquisa web: "Cadin Brasil" Murtosa | Sem resultados. **A associação a Murtosa não foi confirmada e não é usada na apresentação.** |
| Pesquisa web: Facebook, TikTok, Google Maps, Aveiro, Ovar, Estarreja | Sem resultados sobre a marca. |

### O que foi confirmado

- A conta `@cadin_do_brasil` existe no Instagram.
- O nome público da conta é "Cadin do Brasil" com as bandeiras do Brasil e de Portugal. É o único sinal verificado de posicionamento: **uma marca brasileira em Portugal**.

### O que não foi possível confirmar

Logótipo, cores, tipografia, estilo fotográfico, produtos, preços, região de atuação, contactos e métodos de encomenda.

### Decisões provisórias (a substituir quando houver material oficial)

1. **Logótipo:** wordmark tipográfico "Cadin / do Brasil" em Bricolage Grotesque. Substituível em `src/js/config.js` (`logoCadin`).
2. **Paleta "Brasil em Portugal":** escolhida a partir do próprio assunto, já que a paleta real não foi confirmada.

   | Nome | Hex | Origem da escolha |
   |---|---|---|
   | Verde Atlântico | `#0F3D2E` | o verde comum às bandeiras do Brasil e de Portugal |
   | Ouro de fritura | `#F4B23E` | a crosta dourada da coxinha; o amarelo brasileiro |
   | Cobalto de azulejo | `#1E4AA8` | o azulejo português (também presente no Brasil colonial); casa com o azul da FastApp e com as toalhas aos quadrados azuis das fotografias |
   | Goiabada | `#D6324A` | acento quente para destaques e alertas |
   | Brigadeiro | `#2B1A14` | texto escuro e fundos quentes |
   | Papel | `#FFF8EC` | superfícies claras |

   Todas as cores estão definidas em `src/styles/deck.css` (`:root`) e podem ser trocadas de uma só vez.
3. **Produtos e preços:** catálogo com produtos típicos de uma salgaderia brasileira (coxinha de frango, coxinha com queijo, esfiha, pão de queijo, brigadeiros, caixas para festa). **São exemplos, não o catálogo da Cadin**, e estão assinalados como ilustrativos no website demonstrativo. Editáveis em `src/js/data.js`.
4. **Clientes, encomendas, stock e receitas:** todos fictícios e assinalados como "Demonstração conceptual".

### Fotografias ilustrativas usadas

Fotografias com a [Unsplash License](https://unsplash.com/license), que permite uso comercial gratuito. Cada slide com fotografias mostra a etiqueta **"Imagens ilustrativas"**, que se desliga em `config.js` (`avisoImagemIlustrativa: false`) quando forem substituídas por fotografias da Cadin.

| Ficheiro | Conteúdo | Autor (Unsplash) | ID da foto |
|---|---|---|---|
| `hero-coxinha.jpg` | coxinha aberta com recheio | Léo Roza | photo-1641848462639-88ff847243dc |
| `encerramento.jpg`, `coxinha-aberta.jpg` | coxinhas, uma aberta | Léo Roza | photo-1641848462222-52f272bd6cfc |
| `coxinhas-mesa.jpg` | coxinhas em prato de ardósia | Léo Roza | photo-1641848462730-85ef2de72273 |
| `coxinha-queijo.jpg` | coxinha com queijo | Léo Roza | photo-1641848462443-5e24914f9b3e |
| `esfihas.jpg` | esfihas | Léo Roza | photo-1641848391983-a60bafeaa315 |
| `esfiha-mao.jpg` | esfiha na mão | Léo Roza | photo-1641848392485-c0ed20c4556d |
| `coxinha-studio.jpg` | coxinha em fundo liso | Guilherme Gomes Dos Santos | photo-1718897266403-5d2030c313e6 |
| `pao-de-queijo.jpg` | pão de queijo com café | rodolfo allen_ | photo-1559141680-d0bd7bc5af84 |
| `brigadeiros.jpg` | brigadeiros com granulado | Felippe Lopes | photo-1702982841001-f65535a5a40b |
| `brigadeiros-gourmet.jpg` | brigadeiros gourmet | Ediglecio Lêla | photo-1630953900039-960a64b49176 |
| `brigadeiros-torre.jpg` | brigadeiros em forminhas | Ediglecio Lêla | photo-1630953899906-d16511a72558 |
| `brigadeiros-mao.jpg` | brigadeiros na mão | João Pedro Freitas | photo-1565814598158-c9e60d235405 |
| `docinhos-festa.jpg` | docinhos de festa | Jonathan Borba | photo-1767396867485-7e41ee6fec97 |

Para voltar a descarregar: `npm run photos` (script `tools/fetch-photos.mjs`).

### Fotografias a pedir à Cadin para finalizar

Formato horizontal ou vertical indicado; resolução mínima recomendada entre parênteses.

| Substitui | Pedido | Formato |
|---|---|---|
| `hero-coxinha.jpg` | o produto-estrela, de perto, com recheio visível | vertical (1500 × 2250) |
| `encerramento.jpg` | mesa ou bancada com vários produtos | **horizontal** (2200 × 1460) |
| `coxinha-studio.jpg` | um salgado sobre fundo liso e claro | vertical (1000 × 1250) |
| `coxinha-aberta.jpg`, `coxinha-queijo.jpg` | variedades de salgados | horizontal (1000 × 670) |
| `coxinhas-mesa.jpg`, `esfihas.jpg`, `esfiha-mao.jpg`, `pao-de-queijo.jpg` | outros salgados do catálogo real | vertical (900 × 1350) |
| `brigadeiros*.jpg`, `docinhos-festa.jpg` | doces e caixas para festas | vertical (900 × 1200) |
| logótipo | ficheiro vetorial (SVG ou PDF) ou PNG com fundo transparente, versões clara e escura | — |

Também a pedir: lista real de produtos e preços, contacto de encomendas, zona de entrega e se aceitam encomendas para festas.

---

## 2. FastApp

### Fontes consultadas

| Fonte | O que forneceu |
|---|---|
| [fastapp.cloud](https://www.fastapp.cloud/): meta tags e código público do site | posicionamento, textos dos serviços, paleta, tipografia, contacto |
| `img/a2ea4eef-…jpg` (publicação "Inteligência Artificial na FastApp", fornecida) | logótipo com wordmark, uso de cores sobre preto |
| `img/Apresentação.pptx` (apresentação institucional, fornecida) | símbolo vetorial oficial, cores e fontes da apresentação |

### Identidade

- **Logótipo:** símbolo de duas chavetas `{ }`, a da direita a desfazer-se em píxeis. Wordmark "Fast" + "App" (com "App" em azul-claro) e "CLOUD" espaçado por baixo. Os vetores oficiais estão em `assets/logos/` e embutidos em `src/js/icons.js`.
- **Cores do site atual:** fundo `#05070D`, superfícies `#0C111C`, texto `#F2F6FF`, acento `#8FD3E8`, acento forte `#2F5BEA`.
- **Cores da apresentação institucional:** azul-marinho `#011C43`, azul-claro `#96D8E9`, `#101728`.
- **Tipografia do site:** Space Grotesk (títulos), Inter (texto), JetBrains Mono (detalhes). A apresentação institucional usa Montserrat e Poppins.

### Posicionamento e linguagem (textos públicos do site)

- "Agência e Consultoria de IA."
- "A IA evolui todo dia. Você cuida do seu negócio — a gente cuida da IA por você."
- "A FastApp é o seu departamento de IA terceirizado: estratégia, implementação e evolução contínua."
- "Do dashboard ao agente de IA — a gente constrói."
- Ferramenta própria: **FastApp Cloud**, um builder para transformar a operação do cliente em software.
- Exemplos de casos no site: gestão de stock e preços com previsão de procura; agente de IA integrado no WhatsApp; painel de insights em tempo real.
- A apresentação institucional descreve a FastApp como plataforma low code, com implementação na nuvem ou local.

O site é escrito em português do Brasil; a apresentação para a Cadin está em português de Portugal, por ser dirigida a um negócio em Portugal.

### Contacto

- Website: **fastapp.cloud**
- E-mail **contato@fastapp.com.br**: encontrado no código público do site. **Confirmar antes da reunião** (o domínio do e-mail difere do domínio do site). Configurável em `src/js/config.js`.
- O site tem um widget de WhatsApp com um número de exemplo (`wa.me/00000000000`), por isso nenhum telefone foi usado.

---

## 3. Decisões de direção criativa

**Ideia central:** *"O sabor do Brasil, a um toque."* A Cadin já tem o sabor, que atravessou o Atlântico; a FastApp encurta o último passo, do desejo à encomenda.

**Conceito visual: azulejos.** O azulejo é um motivo português que também está presente no Brasil e funciona como metáfora do sistema. São quatro peças (website, publicações, encomendas, stock) que só completam o desenho quando encaixam. O padrão foi desenhado de raiz em SVG: os círculos dos cantos e das arestas só ficam completos quando os azulejos se juntam. Aparece:

- na faixa da abertura;
- no encaixe das quatro soluções, onde o círculo central completo revela o símbolo FastApp;
- no mosaico de benefícios;
- nas etapas de implementação, como peças assentes uma a uma;
- na assinatura final.

**A FastApp como parceira, não protagonista.** A identidade da FastApp aparece na abertura (assinatura discreta), no encaixe das soluções, na etapa de implementação e no encerramento (logótipo, cartão de contacto com as cores do site). Os restantes slides vestem a identidade provisória da Cadin.

**Tipografia:** Bricolage Grotesque (títulos expressivos com ar artesanal) para a voz da Cadin; Inter para as interfaces demonstrativas (é a fonte do site da FastApp, o que torna coerente que sejam produtos FastApp); Space Grotesk nos momentos FastApp. Todas com licença SIL Open Font License e incluídas localmente.

**Evitado de propósito:** fundo escuro com gradientes roxos, cartões iguais com ícones genéricos, números de crescimento sem fonte, promessas de publicação automática irrestrita.

## 4. Limitações

1. A identidade visual da Cadin não pôde ser verificada (Instagram fechado sem sessão, sem outros canais públicos encontrados). Toda a identidade da Cadin na apresentação é provisória.
2. As fotografias não são da Cadin. Estão assinaladas e devem ser substituídas antes da reunião, se possível.
3. Os produtos e preços são exemplos típicos do segmento, não o catálogo real.
4. O e-mail da FastApp deve ser confirmado.
