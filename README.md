# 🖼️ Processamento Digital de Imagens — Projeto 1

Projeto desenvolvido para a disciplina de **Processamento Digital de Imagens**, implementado em Python com Jupyter Notebook. Abrange operações fundamentais de PDI como conversão de espaços de cor, manipulação de matiz e saturação, geração de negativos e aplicação de filtros por correlação.

---

## 📖 Descrição

O notebook implementa **quatro questões** práticas sobre processamento de imagens, todas desenvolvidas **sem o uso de funções prontas de bibliotecas** para os algoritmos principais, com exceção de leitura/exibição de imagens.

---

## 📋 Questões

### Questão 1 — Conversão RGB → HSV → RGB
Converte cada pixel de uma imagem do espaço de cor **RGB para HSV** (Hue, Saturation, Value) e em seguida de volta para **RGB**, verificando a fidelidade da conversão.

- Implementação manual das funções `rgbToHSV` e `hsvToRGB`
- Tratamento de casos especiais (pixel acromático, divisão por zero)
- Clamp dos valores RGB ao intervalo [0, 255]

### Questão 2 — Alteração de Matiz e Saturação no HSV
Converte a imagem para HSV e **altera manualmente os valores de Matiz (H) e Saturação (S)**, depois converte de volta para RGB.

- Matiz fixado em **120° (verde)**
- Saturação fixada em **1.0 (máxima)**
- Permite visualizar o efeito isolado de cada componente HSV

### Questão 3 — Imagem Negativa
Aplica o efeito negativo de **duas formas distintas**:

- **Negativo em RGB:** inverte cada canal diretamente (`255 - valor`)
- **Negativo pela banda V do HSV:** converte para HSV, inverte apenas o canal V (`255 - V`) e reconverte para RGB

### Questão 4 — Correlação m×n com Stride
Implementa correlação 2D configuraável por arquivo de texto externo, aplicada canal a canal (R, G e B), com suporte a **stride (passo)**.

Filtros testados:
| Filtro | Descrição |
|---|---|
| **Box** | Suavização por média; testa variações 1×10, 15×15, 15×1 e 1×15 |
| **Sobel Vertical** | Detecção de bordas na direção vertical |
| **Sobel Horizontal** | Detecção de bordas na direção horizontal |

Análises realizadas:
- Comparação visual e de **tempo de processamento** entre `Box15×15` e `Box15×1` → `Box1×15` (filtros separáveis)
- Pós-processamento do Sobel: valor absoluto + expansão de histograma para [0, 255]

---

## 🛠️ Bibliotecas utilizadas

| Biblioteca | Uso |
|---|---|
| `Pillow (PIL)` | Leitura, exibição e conversão de imagens |
| `NumPy` | Operações matriciais (questão 4) |
| `Matplotlib` | Visualização das imagens |
| `colorsys` | Referência (não utilizada diretamente nos algoritmos) |
| `OpenCV (cv2)` | Importado como referência |
| `time` | Medição do tempo de processamento (questão 4) |

---

## 🚀 Como executar

1. Clone o repositório:

```bash
git clone https://github.com/PedroBrock/PDI.git
cd PDI
```

2. Instale as dependências:

```bash
pip install pillow numpy matplotlib opencv-python
```

3. Certifique-se de que as imagens estão na pasta `imagens/` e os arquivos `.txt` de filtro estão na raiz do projeto.

4. Abra e execute o notebook:

```bash
jupyter notebook Projeto1_PDI.ipynb
```

---

## 📚 Referências

- GONZALEZ, R. C.; WOODS, R. E. *Processamento Digital de Imagens*. 3. ed. Pearson, 2010.
- [Documentação Pillow](https://pillow.readthedocs.io/)
- [Documentação NumPy](https://numpy.org/doc/)

---

## 👨‍💻 Disciplina

> Processamento Digital de Imagens
