# Corpus de Keyframes em Libras

## Descrição

O corpus foi construído para apoiar pesquisas em tradução automática entre Língua de Sinais (Libras) e Língua Oral (Português Brasileiro), a partir do reconhecimento de sinais. Ele reúne um conjunto sistemático de keyframes derivados de vídeos de execução de sinais da Língua Brasileira de Sinais (Libras).

## Composição

### Características do Corpus

- **Número de sinais**: 25 sinais distintos de Libras, selecionados a partir de vocabulário educacional de uso frequente
- **Número de intérpretes**: 11 intérpretes proficientes em Libras participaram da coleta, garantindo diversidade de estilo e variações individuais de execução
- **Gênero dos intérpretes**: 7 mulheres e 4 homens
- **Faixa etária dos intérpretes**: 
  - Mulheres: 25 a 45 anos
  - Homens: 20 a 40 anos
- **Repetições por intérprete**: cada intérprete executou 10 repetições de cada sinal, totalizando 110 repetições por sinal

### Sinais que Compõem o Corpus

#### SINAIS DO CORPUS

| ÂNGULO       | APOSTILA       | CONTEXTO     | CURSO        | ESTUDAR    |
|--------------|----------------|--------------|--------------|------------|
| ADIÇÃO       | BIOLOGIA       | CLASSE       | DISCIPLINA   | FILOSOFIA  |
| APONTADOR    | BOLSA_DE_ESTUDO| COESÃO       | DICIONÁRIO   | FÍSICA     |
| ANTROPOLOGIA | CAPÍTULO       | COERÊNCIA    | ENSINAR      | GEOGRAFIA  |
| ALUNO        | CONCEITO       | COLEGA       | ESCOLA       | HISTÓRIA   |

- **Maior sinal do corpus**: 11 segundos (328 frames)
- **Menor sinal do corpus**: 1 segundo e 30 frames

### Total de Instâncias

25 sinais × 10 intérpretes × 10 repetições = **2.500 instâncias** de sinais no corpus.

## Aquisição e Extração

### Parâmetros de Captura

- **Taxa de captura original**: 30 quadros por segundo (30 FPS)
- **Resolução dos vídeos**: Os vídeos têm resoluções diferentes (especificadas no CSV)

### Processo de Extração

Os vídeos foram processados para identificar **keyframes representativos** de cada sinal, ou seja, quadros que descrevem de forma mais clara e estável a configuração de mão, movimento e expressão facial relevantes.

#### Ferramenta Utilizada

- **MediaPipe**: Ferramenta usada para extração dos keyframes

#### Metodologia

- Cada execução do sinal foi segmentada em um conjunto reduzido de keyframes que preservam a sequência linguística essencial, reduzindo redundância visual
- Para cada keyframe são extraídas as seguintes informações:
  - **x**: posição horizontal
  - **y**: posição vertical
  - **z**: proximidade estimada
  - **visibility**: visibilidade do keyframe

### Mapeamento de Keypoints

Os IDs dos keyframes seguem o seguinte esquema:
## Índices de Keypoints do Corpo Humano

| Índice | Parte do corpo            |
|--------|---------------------------|
| 0      | nose                      |
| 1      | left eye (inner)          |
| 2      | left eye                  |
| 3      | left eye (outer)          |
| 4      | right eye (inner)         |
| 5      | right eye                 |
| 6      | right eye (outer)         |
| 7      | left ear                  |
| 8      | right ear                 |
| 9      | mouth (left)              |
| 10     | mouth (right)             |
| 11     | left shoulder             |
| 12     | right shoulder            |
| 13     | left elbow                |
| 14     | right elbow               |
| 15     | left wrist                |
| 16     | right wrist               |
| 17     | left pinky                |
| 18     | right pinky               |
| 19     | left index                |
| 20     | right index               |
| 21     | left thumb                |
| 22     | right thumb               |
| 23     | left hip                  |
| 24     | right hip                 |
| 25     | left knee                 |
| 26     | right knee                |
| 27     | left ankle                |
| 28     | right ankle               |
| 29     | left heel                 |
| 30     | right heel                |
| 31     | left foot index           |
| 32     | right foot index          |

![Esquema de Keypoints](./nvhvrq0k.png)

## Formato e Organização

### Estrutura de Dados

Os keyframes são organizados por **sinal**, **intérprete** e **repetição**, mantendo metadados que permitem análise comparativa entre diferentes realizadores e repetições.

### Metadados Associados

Cada instância possui anotações associadas, incluindo:

- Identificação do sinal
- Identificação do intérprete
- Número da repetição
- Ordem sequencial dos keyframes extraídos
- Nome do arquivo associado
