# Documentação do Projeto: Ilustração SVG Low Poly

Este documento descreve a estrutura técnica de um gráfico vetorial escalável (SVG) construído inteiramente com polígonos e estilos CSS internos.

---

## 1. Estrutura Visual e Layout
A aplicação utiliza um contêiner Flexbox para centralizar o elemento visual na tela:
* **Contêiner**: A classe `.contenedor` garante o alinhamento central vertical e horizontal.
* **SVG**: Definido com um `viewBox="-132 160.8 346.8 472.2"`, permitindo que a ilustração seja redimensionada sem perda de qualidade.
* **Simetria**: O código é dividido em dois grupos principais de IDs:
    * `<g id="Izquierda">`: Contém os polígonos do lado esquerdo.
    * `<g id="Derecha">`: Contém os polígonos do lado direito.

---

## 2. Estilização (CSS)
O projeto utiliza classes CSS sequenciais (`.st0` até `.st59`) para aplicar cores sólidas (`fill`) aos polígonos. 
* **Cores**: A paleta varia entre tons de azul profundo, roxo, cinza e cores pastéis.
* **Filtros**: Existe um filtro de SVG definido nos `<defs>` com o ID `edgeClean`. Ele utiliza `feComponentTransfer` para suavizar as bordas dos polígonos e evitar frestas brancas entre as junções das formas geométricas.

---

## 3. Elementos Gráficos
A ilustração é composta por centenas de elementos `<polygon>`, cada um definido por um conjunto de pontos (`points`).

### Destaques da Anatomia:
| Elemento | Característica |
| :--- | :--- |
| **Olhos** | Localizados nos grupos `#Ojo-izquierdo` e equivalentes, utilizando caminhos (`path`) e círculos para dar expressão à figura. |
| **Filtro de Bordas** | Aplicado via `filter="url(#edgeClean)"` em ambos os grupos laterais. |
| **Escalabilidade** | O CSS define `width: 200px; height: auto;` para o SVG, facilitando a integração em diferentes tamanhos de tela. |

---

## 4. Técnica de Implementação
Esta técnica é comum em arte digital moderna e design de interfaces, onde:
1. Uma imagem complexa é decomposta em triângulos e quadriláteros.
2. Cada forma recebe uma cor baseada na iluminação da cena original.
3. O resultado é um arquivo leve, com carregamento rápido e resolução infinita.

---

> **Dica de Customização**: Para alterar as cores da ilustração, basta modificar os valores hexadecimais no bloco `<style>` do cabeçalho, sem precisar mexer nas coordenadas dos polígonos.
<img width="512" height="371" alt="Image" src="https://github.com/user-attachments/assets/e67ae376-1795-451a-9baf-01f95ed2f5b2" />
