# Inserção (foco no tio)

## Passo 0: Faça uma inserção BST comum, inicialmente pintando o nó recém-inserido de vermelho.
- Seja `z` o nó folha recém inserido:

### Caso 1 - Tio Vermelho
* **O que fazer:** Pai e tio ficam pretos, e o avô fica vermelho.
* **Próximo passo:** Ponteiro `z` sobe para o avô e recomeça.

### Caso 2 - Tio Preto e `z` filho formando joelho
* **O que fazer:** Rotação do pai em sentido oposto à `z`.
* **Próximo passo:** O antigo pai vira o novo `z` e prosseguimos para o caso 3.

### Caso 3 - Tio Preto e `z` filho em linha reta
* **O que fazer:** O pai fica preto, o avô fica vermelho, depois rotacionamos o avô em sentido oposto ao pai de `z`.
* **Próximo passo:** Pinte a raíz de preto e encerre aqui.

---

# Remoção (foco no irmão)

## Passo 0: Faça uma remoção BST comum. Se o nó removido era preto, prossiga com os passos abaixo. Se o nó removido tinha 1 ou 0 filhos, `x` será o nó que substituiu o nó removido; Se o nó removido tinha 2 filhos, `x` apontará para a posição original do nó que substituiu o nó removido.

### Caso 1 - Irmão vermelho
* **O que fazer:** O irmão fica preto, o pai fica vermelho, rotacionamos o pai na direção de `x`.
* **Próximo passo:** Prosseguir para o caso 2, 3 ou 4 (o primeiro aplicável).

### Caso 2 - Irmão com 2 filhos pretos
* **O que fazer:** O irmão fica vermelho.
* **Próximo passo:** Ponteiro `x` sobe para o pai e recomeça.

### Caso 3 - Irmão com filho interno vermelho
* **O que fazer:** Filho interno do irmão fica preto, irmão fica vermelho e rotacionamos o irmão para o lado externo (lado oposto de `x`).
* **Próximo passo:** Prosseguimos para o caso 4.

### Caso 4 - Irmão com filho externo vermelho
* **O que fazer:** O irmão copia a cor do pai, o pai fica preto, o filho externo do irmão fica preto e rotacionamos o pai na direção de `x`.
* **Próximo passo:** Pinte o nó `x` final de preto (se for não-nulo) e encerre aqui.