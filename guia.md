# Inserção (foco no tio)

## Passo 0: Faça uma inserção BST comum, inicialmente pintando o nó recém-inserido de vermelho.
- Seja `z` o nó folha recém-inserido. Enquanto o pai de `z` for vermelho, execute (se o pai for preto, pinte a raiz de preto e encerre):

### Caso 1 - Tio Vermelho
* **O que fazer:** Pai e tio ficam pretos, e o avô fica vermelho.
* **Próximo passo:** Ponteiro `z` sobe para o avô e recomeça.

### Caso 2 - Tio Preto e `z` filho formando joelho
* **O que fazer:** Rotação do pai em sentido oposto a `z`.
* **Próximo passo:** O antigo pai vira o novo `z` e prosseguimos para o Caso 3.

### Caso 3 - Tio Preto e `z` filho em linha reta
* **O que fazer:** O pai fica preto, o avô fica vermelho, depois rotacionamos o avô em sentido oposto ao pai de `z`.
* **Próximo passo:** Pinte a raiz de preto e encerre aqui.

---

# Remoção (foco no irmão)

## Passo 0: Faça uma remoção BST comum:
- **0 ou 1 filho:** `x` é o filho que ocupou o lugar do nó removido. Se o nó removido era preto, prosseguimos com os passos abaixo.
- **2 filhos:** O sucessor substitui o nó removido e copia a cor dele; `x` aponta para a posição antiga que o sucessor deixou. Se a cor original do sucessor era preta, prosseguimos com os passos abaixo.
- **Enquanto `x` não for a raiz e `x` for preto**, execute (se `x` for vermelho ou for a raiz, pinte `x` de preto e encerre):

### Caso 1 - Irmão vermelho
* **O que fazer:** O irmão fica preto, o pai fica vermelho, rotacionamos o pai na direção de `x` (o novo irmão de `x` passa a ser o antigo sobrinho interno).
* **Próximo passo:** Prosseguir para o Caso 2, 3 ou 4.

### Caso 2 - Irmão preto com 2 filhos pretos
* **O que fazer:** O irmão fica vermelho.
* **Próximo passo:** Ponteiro `x` sobe para o pai e recomeça.

### Caso 3 - Irmão preto com filho interno vermelho e externo preto
* **O que fazer:** Filho interno do irmão fica preto, irmão fica vermelho e rotacionamos o irmão para o lado externo (lado oposto de `x`; o antigo filho interno vira o novo irmão).
* **Próximo passo:** Prosseguimos para o Caso 4.

### Caso 4 - Irmão preto com filho externo vermelho
* **O que fazer:** O irmão copia a cor do pai, o pai fica preto, o filho externo do irmão fica preto e rotacionamos o pai na direção de `x`.
* **Próximo passo:** Pinte a raiz de preto e encerre aqui.