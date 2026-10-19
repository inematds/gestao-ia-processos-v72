# PLANO — G2 · Processos: processo não é sagrado (v7.2)

Curso G2 da **Formação Gestão de IA 2027** (área https://eventos.inema.pro/gestao-ia/). Contrato: tabela G2 de `~/projetos/ia-2027/estrategia/CURRICULO-GESTAO-IA-2027.md`. Padrão aprovado: piloto G3 `gestao-ia-agentes-v72`. Competência da área: **2 Arquitetura do trabalho** ("Esse processo ainda deveria existir? Eliminar, simplificar, redesenhar, e só então automatizar"), com pontes para a 7 (avaliação) e a 8 (evolução).

**Aluno:** gestor de área, dono de PME, líder de operações. Não programa: redesenha e administra o processo.
**Caso condutor:** Horizonte Distribuidora (`https://inematds.github.io/prof2030-lab/`, empresa fictícia de estudo). O aluno é a **Patrícia Lima, gerente comercial**. Processo: **pedido que chega pelo WhatsApp até o faturamento**. Colegas: Juliana (atendimento), Rafael (TI terceirizada), Carlos (dono). Gancho do curso: o Carlos quer "colocar a Hora também no faturamento, do jeito que está" (no lab ele decide em novembro se amplia o agente para o financeiro, olhando um painel sem linha de base, F11).
**Falhas do lab como problemas de gestão:** F11 painel sem linha de base (aulas 2 e 6), F7 sem registro nem aprovação acima de R$ 5 mil (aulas 3 e 4: aprovação é etapa que fica), F5 desconto sem teto (aula 4: a conferência de preço vira exceção), F12 IA na sombra (aula 2: o processo de proposta com chatbot pessoal), F10 resumo para API estrangeira (aula 2: risco na matriz).
**Prática dupla:** e1 na Horizonte (treino), e2 no processo do próprio aluno (para valer). O mapa (aula 3) e o canvas atual × futuro (aula 8) são os modelos centrais e servem para o processo real do aluno.

## Fontes (não alteradas)
- `~/projetos/curso-gestao-ia/planejamento/PLANO-CURSO.md` mód. 1 (1.1–1.4, laboratório "entrevistar o dono, acompanhar cinco casos, caminho normal e dois desvios; medir volume, minutos por caso, retrabalho e espera"; entrega canvas atual e futuro; critério de aceite), mód. 10 (LOOP-R: mudança não é aplicada por feedback isolado, versão anterior identificada). `METODO.md` (contrato do processo, contrato de mudança, indicadores com denominador, capacidade liberada ≠ economia, níveis 0–4). `TEMPLATES.md` (canvas de processo, experimento LOOP-R).
- `~/projetos/pffia` (Arquiteto de Trabalho com IA): IA em cima do processo antigo × redesenho; "esta etapa precisa existir se um agente fizer as três anteriores?"; etapas que só existem pela passagem de mão; julgamento, exceção, supervisão, estratégia; regra × julgamento ("duas pessoas bem treinadas chegariam à mesma resposta?"); três perguntas para escolher processo; seis elos.
- `~/projetos/copilot-agentic`: cadeia trabalho → processo → workflow → agente; aprovação humana rara e importante (aprovar tudo = aprovar sem ler); quatro escolhas para entrar num sistema, nesta ordem: porta de serviço/API, fluxo com conector, automação de tela, Computer Use (com aprovação antes de gravar).
- `~/projetos/inemaeventos/gestao-ia/index.html` §01 mudança 2 ("o processo antigo não merece ser acelerado"; "se eu tivesse humanos, agentes e automações hoje, esse processo ainda existiria desse jeito?"), §04 competência 2, §05 (quatro gerações de processo; regras 1, 2 e 3).
- `~/projetos/loop-r`: versões v1, v2, "atual"; promover e reverter; nenhuma versão pior entra por decisão do sistema; ledger.
- `~/projetos/prof2030-lab`: peças `agente-whatsapp`, `painel` (indicadores.json), `inventario.html`, `resumo-atendimento`, gabarito.
- Mercado: `mercado-gestao-ia-2026-10.md` e `mercado-ia-2026-10.md` (só fatos sem [incerto]; Sinch fora).

## Política fictícia da Horizonte (igual ao G3; sempre rotulada)
- Tabela: detergente neutro 5 L R$ 38,90; desinfetante lavanda 5 L R$ 42,50. Caixa = 6 galões.
- Desconto: até 5% a Hora concede sozinha a cliente cadastrado; de 5% a 10% a Patrícia aprova; acima de 10% só o Carlos.
- Pedido acima de R$ 5 mil: aprovação da Patrícia antes de separar.
- Marcar como pago, mudar preço, cadastrar cliente novo, apagar conversa: nunca pela Hora.
- Níveis de autonomia 0–4 do METODO.

## O processo da Horizonte (fictício, criado para este curso, coerente com o lab)

**v1.0 — como é hoje (13 etapas):**
1. Cliente pede pelo WhatsApp; a Hora (ou a Juliana) responde.
2. A Hora monta o pedido no app Horizonte Pedidos.
3. A Juliana copia o pedido do app para a planilha do comercial. *(hábito: a planilha nasceu antes do app)*
4. A Patrícia confere preço e desconto de **todos** os pedidos na planilha. *(nasceu em 14/10, depois dos incidentes c-201 e c-202; vale para todos, inclusive os de tabela)*
5. Pedido acima de R$ 5 mil: a Patrícia aprova. *(exigência real: política)*
6. A Juliana imprime o pedido e leva ao estoque. *(passagem de mão)*
7. O estoque confere a disponibilidade no GestorPlus (ERP).
8. Separação.
9. O estoque avisa a Juliana por WhatsApp que separou. *(passagem de mão)*
10. A Juliana manda e-mail ao financeiro com o pedido. *(passagem de mão)*
11. O financeiro redigita o pedido no GestorPlus. *(só existia porque o app não fala com o ERP)*
12. O financeiro confere o cadastro (CNPJ, endereço) e emite a nota. *(exigência real: nota fiscal; a conferência está no lugar errado)*
13. A Juliana manda a nota ao cliente pelo WhatsApp.

**Desvios:** D1 cliente sem cadastro completo → o financeiro devolve ao atendimento na etapa 12 (o pedido já foi separado); D2 falta de produto na etapa 7 → pedido parcial, a Juliana avisa o cliente. **Decisões:** desconto dentro da alçada? valor acima de R$ 5 mil? cliente cadastrado? tem estoque?

**Cinco casos acompanhados (15 a 17/10/2026, depois dos incidentes; fictícios; exploração, não amostra):**

| caso | caminho | minutos de gente | pedido confirmado → nota | voltou do faturamento? |
|---|---|---|---|---|
| P1 Padaria Pão Dourado, R$ 1.240 | normal | 16 | 22 h | não |
| P2 Supermercado Bom Preço, R$ 4.320, pede 8% | decisão de desconto (Patrícia) | 21 | 26 h | não |
| P3 Vale Verde, cliente novo sem CNPJ, R$ 2.800 | D1 | 38 | 75 h | sim |
| P4 Restaurante Sabor da Serra, falta desinfetante | D2 | 27 | 49 h | não |
| P5 Clínica Bem Viver, R$ 6.150 | aprovação acima de R$ 5 mil | 19 | 30 h | não |

Mediana: 21 min de gente; 30 h até a nota. Volume: 168 pedidos fechados na semana de 13/10 (painel do lab). Devolução pelo faturamento: "uns 15 por semana" (declarado pelo financeiro, não contado → hipótese, ≈ 9% de 168).

**v2.0 — redesenhada (8 etapas):** 1 pedido pelo WhatsApp → 2 a Hora monta no app **só para cliente com cadastro completo**; cliente novo vai para a Juliana cadastrar antes (verificação movida para a entrada) → 3 a política da empresa (5%, 10%, R$ 5 mil) vira regra fixa do sistema (escrever a matriz ação por ação é o G3); a Patrícia vê **só** as exceções (5–10%, acima de R$ 5 mil) + amostra semanal de 10 pedidos verdes → 4 estoque recebe o pedido na tela (fim do papel) → 5 separação, com baixa no app (fim do aviso por WhatsApp) → 6 pedido vai do app para o ERP sem redigitação (como entra: aula 5) → 7 financeiro confere e emite a nota → 8 nota sai ao cliente pela conversa, com registro. Cortadas: 3, 6, 9, 10, 11. Simplificada: 4 (todos → exceções + amostra). Movida: conferência de cadastro (12 → 2). Fica: 5 (exigência), 12 (nota).

## As 8 aulas

| # | slug | aula | objetivo (≤160) | diagrama | prática ("pronto quando") | extra |
|---|---|---|---|---|---|---|
| 1 | `nao-acelere` | Não acelere o processo antigo | explicar por que automatizar um processo ruim entrega o erro mais rápido e marcar as etapas que existem só por hábito | escada das 4 gerações de processo (área §05) | e1 classificar as 13 etapas da Horizonte (hábito, exigência real, passagem de mão); e2 1 processo seu com ≥3 etapas "por hábito" marcadas e o motivo | o pedido do Carlos como gancho |
| 2 | `primeiro-processo` | Escolher o primeiro processo | priorizar processos por valor, viabilidade e risco numa matriz e justificar o escolhido por escrito | funil: 3 perguntas → matriz → escolhido + recorte | e1 matriz dos 5 processos da Horizonte; e2 matriz de 5 processos seus com o escolhido justificado | KPMG 04/2026: 45% com projetos desconectados |
| 3 | `mapear` | Mapear o que acontece de verdade | mapear o caminho normal, os desvios, as decisões e as medidas de hoje de um processo, a partir de casos acompanhados | mapa em 6 blocos (rolagem guiada): gatilho → caminho normal → decisões → desvios → medidas → conclusão | e1 mapa "pedido pelo WhatsApp → faturamento" com 2 desvios e medidas dos 5 casos; e2 mapa do seu processo com 5 casos acompanhados | modelo central: mapa de uma página + roteiro de entrevista |
| 4 | `redesenhar` | Eliminar, simplificar, redesenhar | desmontar o processo antes de automatizar: cortar, simplificar e mover etapas, com o motivo de cada mudança | escada eliminar → simplificar → redesenhar → só então automatizar | e1 v2 da Horizonte com etapas cortadas e motivo de cada corte; e2 a versão redesenhada do seu | **simconversa** (Carlos quer IA no processo do jeito que está) |
| 5 | `quem-faz` | Quem faz cada etapa | decidir, etapa por etapa, se fica com pessoa, automação simples, agente, Computer Use ou integração por API, com o motivo | escada de decisão: julgamento? → regra fixa? → sistema tem porta? → tela estável? → Computer Use | e1 quadro etapa × executor × motivo da v2; e2 o seu quadro | Microsoft WTI 2026: 16% Frontier Professionals |
| 6 | `linha-de-base` | Linha de base e meta | definir 3 indicadores com numerador, denominador e valor de hoje, observado ou marcado como hipótese, antes de mexer | fração: numerador / denominador + período + origem → hoje → meta | e1 corrigir o painel F11 com 3 indicadores e o guarda-corpo; e2 os 3 do seu processo | painel F11 do lab |
| 7 | `versao` | Processo com versão | registrar a mudança v1 → v2 com motivo, evidência, aprovador e o jeito de voltar, como se faz com software | ciclo v1 em uso → proposta → teste → decisão → v2 ou reversão (volta) | e1 registro v1.0 → v2.0 da Horizonte; e2 o seu registro | LOOP-R |
| 8 | `canvas` | Projeto: o processo redesenhado + O que mudou | entregar o canvas atual × futuro do seu processo, com recorte do piloto, e aprová-lo pela rubrica | canvas = 5 blocos + rubrica → aprovado ou volta (rubrica com blocos que o G5 reaproveita: itens 1 e 2 do §2 do currículo — processo com dono, entrada, conclusão e linha de base; etapas cortadas com motivo) | e1 canvas da Horizonte aprovado (≥75 + 5 obrigatórios); e2 canvas do seu processo; e3 plano datado | "O que mudou" (out/2026), `mapa` (4 degraus) + `gerador` |

Rodapé da aula 8: seção `texto` "Certificação": "Certificação INEMA de qualificação 'Gestor de IA', em breve no cert.inema.pro. Não é certificação profissional regulada."

## A simconversa da aula 4 — "o Carlos quer a Hora no faturamento"

Personagem: **Carlos Mendes · dono** (simulação). Estrutura linear; só algumas falas têm atalho para um fim ruim (caminho mais curto, soma menor). Melhor caminho = 2 + 2 + 2 + 2 + 2 = **10**.

| fala | o Carlos diz | opções (nota → destino) |
|---|---|---|
| `abre` | quer a Hora no faturamento já na segunda, "fazendo igual à Juliana e ao financeiro" | começa segunda (0 → `fim-acelera`) · só nos pedidos pequenos (1 → `etapas`) · uma semana para mapear e perguntar se cada etapa ainda deve existir (2 → `etapas`) |
| `etapas` | "sempre foi assim e funciona" | manter (0 → `fim-manter`) · cortar tudo o que é manual (1 → `conferencia`) · planilha, papel e e-mail só existem pela passagem de mão; cortar com motivo; nota e aprovação ficam (2 → `conferencia`) |
| `conferencia` | e a conferência de preço em todos os pedidos? | a Hora confere os próprios (0) · continuo conferindo todos (1) · a política já diz o que é exceção: confiro só exceções + amostra semanal (2) — todas → `cadastro` |
| `cadastro` | o financeiro devolve pedido sem CNPJ | a Hora completa com o que achar na internet (0 → `fim-dado`) · o financeiro cobra o cliente quando faltar (1 → `medida`) · mover a verificação para a entrada; cliente novo passa pela Juliana antes de separar (2 → `medida`) |
| `medida` | quando eu sei se melhorou? | quando o painel subir (0 → `fim-painel`) · em um mês a gente vê (1 → `fim-vago`) · 4 semanas de linha de base com 3 indicadores, comparar períodos iguais, v1 guardada para voltar (2 → `fim-bom`) |

Somas: `fim-acelera` 0; `fim-manter` ≤ 2; `fim-dado` ≤ 6; `fim-painel` ≤ 8; `fim-vago` ≤ 9; `fim-bom` ≤ 10 (máximo). Nenhum desvio soma fala extra.

## Decisões
- **Vídeo:** nenhum. O currículo atribui os vídeos publicados ao G0, G1 e G5.
- **Capa sem texto** (instrução do brief), como no piloto.
- **Etapas e números da Horizonte** (13 etapas, 5 casos, "uns 15 por semana") foram criados para este curso, coerentes com o lab (168 pedidos fechados na semana de 13/10 vêm do `indicadores.json`) e com a política do G3; sempre rotulados como fictícios. Os 5 casos são exploração, não amostra (PLANO-CURSO mód. 1).
- **Conta do painel (aula 6):** pedidos fechados ÷ atendimentos caiu de 20,1% (141/702, 01/09) para 18,6% (168/901, 13/10): calculado do `indicadores.json` do lab.
- **Aula 5:** a escada de quatro escolhas para entrar num sistema vem do copilot-agentic; o curso não ensina a construir a integração, só a decidir e a pedir.
- `lado_card` aponta para o G0 (`gestao-ia-base-v72`, em produção: 404 esperado no `validar --links`).
