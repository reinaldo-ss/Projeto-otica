---
name: ui-ux
description: Regras acionáveis de UI/UX destiladas de fontes primárias (Nielsen, Tognazzini, NN/g, Smashing, GOV.UK, Bret Victor). Use ao projetar ou revisar qualquer interface — layout, tipografia, cor, contraste, ícones, movimento, estados de erro/carregamento, acessibilidade e microcopy. Também serve como checklist de revisão antes de entregar uma tela.
---

# UI/UX — regras de decisão

Cada regra abaixo veio de uma fonte primária lida e verificada, creditada no fim.
Quando uma regra é numérica, o número é da fonte — não estimativa.

## Como usar

Ao **projetar**: leia a seção do problema em questão antes de escrever código.
Ao **revisar**: rode a checklist final. Uma tela que falha em contraste ou em
estado de erro não está pronta, por mais bonita que esteja.

Regra que domina todas as outras: **nunca sacrifique usabilidade por estética
da moda.** (Tognazzini)

---

## 1. Antes de desenhar

Defina o objetivo do usuário **e** o do negócio antes de abrir o editor. Fluxos
que atendem os dois são os que merecem esforço; nem todo caminho de visitante
merece atenção igual.

Projete **fluxos, não páginas isoladas**. Origens de tráfego diferentes (busca,
anúncio, e-mail, indicação) trazem gente com expectativas diferentes na mesma tela.

Escolha o método de pesquisa pelas 3 dimensões da NN/g:

| Dimensão | Pergunta que responde | Métodos |
|---|---|---|
| Atitudinal vs. comportamental | "o que dizem" vs. "o que fazem" | survey / teste de usabilidade |
| Qualitativo vs. quantitativo | "por quê" vs. "quantos" | entrevista / analytics |
| Contexto de uso | natural, roteirizado, limitado, nenhum | etnografia / benchmark |

O que as pessoas **dizem** e o que **fazem** divergem sistematicamente. Se a
decisão é cara, observe comportamento.

## 2. Layout e hierarquia

Aplique a **Lei de Fitts**: funções importantes ficam grandes; alvos pequenos só
para ações raras. Áreas clicáveis que encostam na borda da tela ganham
profundidade infinita — use isso.

Reduza a **quantidade de alvos** necessários para concluir a tarefa, não só a
distância entre eles.

Navegação visível em todas as telas, com a posição atual destacada. Subtarefas
em overlay, para o contexto principal continuar à vista.

Ofereça **marcos visuais estáveis** — um lugar que pareça "casa" — e uma saída
óbvia de qualquer fluxo.

Grid fluido com media queries; **não** breakpoints fixos por dispositivo. Desenhe
componentes reutilizáveis, não mockups por breakpoint.

**Orçamento de peso da página** é decisão de design, não de infra. Defina o teto
de KB junto com o dev, antes de escolher imagem e fonte.

## 3. Tipografia

Máximo de **2 famílias** para começar; 3 é difícil de acertar. Atribua papel a
cada uma: título, corpo, elemento funcional.

Boas duplas nascem de **contraste**, não de semelhança. Serifada com sem-serifa;
diferenças de largura, peso e estilo. Quanto mais personalidade tem uma, mais
genérica deve ser a outra. Alturas-x parecidas combinam melhor.

Duas fontes da mesma fundição ou do mesmo designer costumam casar de fábrica.

Texto de leitura em alto contraste. Corpo grande o bastante para présbita (45+) —
legibilidade do **dado** vale mais que tamanho do rótulo.

Em rótulos e menus, **palavra-chave primeiro**: usuário experiente reconhece pelo
formato, sem ler.

Nunca use fonte decorativa em texto corrido. Kerning ruim e glifo mal desenhado
não têm conserto.

## 4. Cor e contraste

**Números que valem (WCAG):**

| Alvo | Razão mínima |
|---|---|
| Texto normal | **4,5:1** |
| Texto grande (18pt, ou 14pt negrito) | **3:1** |

Paleta enxuta: **1 a 2 cores** além de branco/preto/cinza. Uma delas é o acento,
usada com parcimônia — se tudo tem ênfase, nada tem.

Comece de cores limpas e vivas; cinza misturado embarreia o resultado. Trabalhe
em RGB para tela, sem converter de CMYK.

**Cor nunca sozinha.** Toda informação transmitida por cor precisa de um segundo
sinal — ícone, texto, forma. Teste com simulador de daltonismo. Mas não elimine
a cor por moda: ela continua sendo canal de comunicação.

### Texto sobre imagem

Cinco técnicas que funcionam, em ordem de eficácia:

1. Overlay semitransparente escurecendo **30–50%**
2. Gradiente (o "floor fade" na parte inferior resolve a maioria dos casos)
3. Desfoque localizado atrás do texto
4. Texto perto da borda, longe do assunto da foto
5. Inverter para texto escuro quando a imagem é clara

Valores que funcionam na prática (Kennedy): overlay preto a **35%**; gradiente de
base ("floor fade") a **20%**. Se a foto é escura e o texto é branco, pode não
precisar de nada — teste antes de empilhar camada.

Teste no **pior quadro** da imagem, não no melhor. Overlay fraco reprova em
acessibilidade mesmo parecendo aceitável a olho nu.

## 5. Ícones

**Ícone obscuro = funcionalidade desperdiçada.** Só três são universais: casa,
impressora e lupa. O resto muda de significado entre plataformas — hambúrguer é
menu ou lista, coração e estrela disputam favorito/nota/salvo.

Regra prática: **rótulo de texto junto do ícone**, visível sem hover. Em touch
não existe hover, então rótulo escondido é rótulo inexistente.

O ícone ganha em velocidade de reconhecimento (~1/10 s) e em economia de espaço;
o texto ganha em ausência de ambiguidade. **Use os dois** — é a única combinação
sem perda.

Cuidado com escala: ícone que ocupa 20% da largura no celular vira 3,5% no
desktop e some.

## 6. Movimento

Anime com propósito declarado. Os nove que se justificam:

orientação · mudança de ação no mesmo lugar · zoom de miniatura para detalhe ·
dica de função escondida · destaque · simulação de dado complexo ·
retorno visual · status do sistema · marca

Movimento tem **a maior proeminência** de qualquer elemento de interface. Por
isso mesmo, use com moderação: anima o que precisa ser notado, não o que está
disponível para animar.

**Tempos de resposta (Tognazzini):**

| Prazo | Obrigação |
|---|---|
| **50 ms** | reconhecer o clique visualmente |
| **2–10 s** | exibir indicador de progresso |

Bloqueie cliques repetidos no mesmo botão para não empilhar fila.

**Curva de aceleração** — relacione ao mundo físico. Objeto que parte do repouso
precisa ganhar velocidade; objeto que vai parar precisa frear:

| Situação | Curva |
|---|---|
| Elemento **saindo** da tela (parte do repouso, acelera) | `ease-in` |
| Elemento **entrando** na tela (chega e freia) | `ease-out` |
| Movimento que começa e termina na tela | `ease-in-out` |

Anime `transform` e `opacity`, que o navegador compõe na GPU. Animar `width`,
`height`, `top` ou `left` força recálculo de layout a cada quadro.

Respeite `prefers-reduced-motion`.

## 7. Estados: erro, espera, conclusão

**Erro** precisa de três coisas, sempre juntas: ser notável, dizer em linguagem
comum o que houve, e apontar a saída. Mensagem que só informa a falha está pela
metade. Sem jargão técnico.

Todo ponto do sistema que exige ação do usuário precisa de tratamento de erro —
inclusive 404 e falha silenciosa de formulário.

**Conclusão** deve ser otimista: mude o estado do botão **na hora**, sem esperar
o servidor. Trate a falha depois, se vier. Percepção de velocidade vale mais que
precisão literal.

**Proteja o trabalho do usuário.** Auto-save contínuo, undo para tudo que é
reversível, e trabalho incompleto sobrevive a logout e novo login. Nunca destrua
dado por formato de entrada incompatível.

## 8. Acessibilidade

Alvo: **WCAG 2.2 nível AA**, funcionando com leitor de tela, ampliador e
reconhecimento de voz.

Acessibilidade **não é de uma pessoa** — é de todo mundo no time, do dev ao
gerente. Planeje a auditoria cedo, não na véspera do lançamento.

Não é só sobre deficiência permanente: conexão ruim, aparelho velho, ambiente
barulhento e recuperação de doença colocam qualquer um na mesma situação.

Nunca desative pinch-zoom "para o bem do usuário".

Inclua pessoas com deficiência na pesquisa — e orce isso (intérprete, transporte,
acompanhante).

## 9. Texto de interface

Copy é a via mais barata de personalidade — e a mais fácil de errar.

Tranquilize onde há atrito: ao pedir dado sensível, diga o que **não** vai
acontecer ("sem spam", "e-mails raros").

Uma palavra muda o registro inteiro: "Tirar fotos" → "Tirar fotos do seu rosto
lindo". Escolha deliberadamente.

Microcopy faz trabalho duplo: explica a função **e** carrega a voz da marca.
"Pedir convite" ≠ "Enviar" — a primeira já gerencia expectativa.

Emoção em interface tem risco. Monitore reação e esteja pronto para recuar.

## 10. Acabamento visual (as 7 regras de Kennedy)

**Luz vem de cima.** Topo do elemento mais claro, base mais escura, sombra
embaixo. É a convenção que o olho lê como relevo — inverter parece defeito.

**Preto e branco primeiro.** Resolva hierarquia, espaçamento e contraste em
escala de cinza; só então adicione cor. Se o layout não funciona sem cor, a cor
está encobrindo um problema de estrutura. Depois entre com uma cor, depois duas,
ou vários tons de um mesmo matiz.

**Dobre o espaço em branco.** O respiro que parece suficiente quase nunca é.
Referências do autor: texto de 12px pede 12px de padding acima e abaixo; espaço
vertical entre itens de menu igual ao **dobro** da altura do texto.

**Pop e un-pop.** Hierarquia não é só aumentar o que importa — é rebaixar o
resto. Sobe: maior, mais pesado, mais contraste. Desce: menor, mais leve, menos
contraste. Regra dura: **só o título da página recebe ênfase máxima.** Todo o
resto precisa dos dois movimentos, senão a página inteira grita.

**Só use fontes boas.** Kennedy sugere Work Sans, Roboto, Metropolis, Source Sans
Pro e IBM Plex Sans como base gratuita segura.

## 11. Dashboards

**Regra dos 5 segundos**: a informação relevante aparece em ~5 s. Se demora mais,
o layout está errado.

**Pirâmide invertida**: insight no topo, tendência no meio, detalhe embaixo.

**5 a 9 visualizações** por dashboard, no máximo. Passando disso, divida em telas
ou use filtro no mesmo widget em vez de duplicar.

Escolha o gráfico pela mensagem: relação · comparação · composição · distribuição.

## 12. Heurísticas de Nielsen — checklist de revisão

Rode antes de entregar. Cada item é uma pergunta de reprovação:

- [ ] **Status visível** — o sistema informa o que está acontecendo, a tempo?
- [ ] **Linguagem do mundo real** — termos do usuário, não do sistema?
- [ ] **Controle e liberdade** — há saída clara, undo e redo?
- [ ] **Consistência** — segue a convenção da plataforma?
- [ ] **Prevenção de erro** — o problema é impedido antes de acontecer?
- [ ] **Reconhecer, não lembrar** — opções visíveis, sem exigir memória?
- [ ] **Flexibilidade** — atalhos para o experiente sem atrapalhar o novato?
- [ ] **Minimalismo** — todo elemento presente disputa atenção com o conteúdo. Algum é dispensável?
- [ ] **Recuperação de erro** — mensagem em linguagem clara, com solução?
- [ ] **Ajuda** — buscável, focada na tarefa, com passos concretos?

Mais quatro, fora da lista de Nielsen, que reprovam com a mesma força:

- [ ] Contraste medido em ferramenta, não a olho (4,5:1 / 3:1)
- [ ] Ícone sem rótulo — existe algum?
- [ ] Estado vazio, de carregamento e de erro — foram desenhados?
- [ ] Teclado: foco visível em tudo que é interativo?

---

## Nota sobre as fontes

Destilado de `awesome-ui` (kevindeasis), lista de 2016 com 334 links. Testei os
143 que carregavam conhecimento: **103 vivos, 40 mortos**. As regras acima vêm de
leitura direta de ~25 fontes primárias que sobreviveram.

**Não confie na lista original sem testar.** Casualidades notáveis: toda a spec do
Material Design (`google.com/design/spec/*`, 12 links) responde 3xx mas cai em
página genérica — o Google desativou na migração para o Material 3. `usability.gov`
foi aposentado. Pixate, Macaw, LayerVault, Code School e InVision não existem mais.

**Erro na direção oposta:** o teste por HTTP marcou como mortos vários links que
estão vivos — Medium e Cloudflare devolvem 403 para requisição automatizada. Foi
o caso das duas partes de *7 Rules for Creating Gorgeous UI*, recuperadas depois
e responsáveis pela seção 10 inteira. Um 403 é suspeita, não atestado de óbito.

Fontes efetivamente lidas: Tognazzini (*First Principles of Interaction Design*) ·
Nielsen (*10 Usability Heuristics*) · NN/g (*text over images*, *icon usability*,
*which UX research methods*) · Smashing Magazine (*functional UX animations*,
*designing flows*, *the personality layer*, *gesture-driven interface*) ·
GOV.UK Service Manual (*accessibility*) · Bret Victor (*Magic Ink*) ·
UX Checklist · Design for Founders (*font pairing*, *color theory*) ·
Tubik Studio (*icons vs copy*) · Sisense (*dashboards*) · UX Mag
(*failing gracefully*, *responsive UX*) · LukeW · ui-patterns.com · Viget · web.dev ·
Erik Kennedy (*7 Rules for Creating Gorgeous UI*, partes 1 e 2) ·
Motion in Interaction (*understanding easing*)

Índice completo dos 103 links vivos: `referencias.md`
