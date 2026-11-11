# RailDesign Studio

Aplicação web para explorar alinhamentos ferroviários, perfis longitudinais, secções transversais e exportações CAD. O repositório contém uma versão distribuída num único ficheiro HTML, com JavaScript e estilos incorporados.

## Funcionalidades presentes no artefacto

- Visualização em planta, perfil e secção, com navegação por PK.
- Representação de vias, carris, plataformas, terreno e estruturas.
- Parâmetros e verificações geométricas.
- Exportação de secções, perfil, planta, eixos 3D e pontos de coordenadas em DXF; os pontos também têm exportação CSV.
- Identificação da proveniência de valores, incluindo `PDF`, `CALC`, `INFERRED`, `SCALED`, `DEMO` e `USER`.

## Abrir localmente

É necessário um navegador moderno. Para servir o ficheiro com Python 3:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Abrir [localhost:8000](http://localhost:8000). Não há instalação npm nem build definido nesta árvore. O HTML inclui fontes externas e Microsoft Clarity; não assumir funcionamento totalmente offline ou ausência de pedidos externos.

## Utilização

1. Explorar o projeto incorporado e selecionar um PK.
2. Consultar planta, perfil e secção, verificando a origem de cada parâmetro.
3. Rever pressupostos e valores de demonstração antes de alterar ou exportar geometria.
4. Escolher o tipo e intervalo de exportação.
5. Abrir o resultado no programa CAD e comparar coordenadas, cotas, escala e unidades com referências independentes.

O código inclui uma alternativa de download pelo navegador e uma integração específica de ambientes que disponibilizem `window.claude`. A disponibilidade de gravação deve ser testada no ambiente utilizado.

## Unidades e validação de engenharia

A exportação documentada no código usa DXF R12, com geometria em metros no espaço de modelo. O perfil pode aplicar exagero vertical e um datum; não interpretar os seus eixos como coordenadas reais sem considerar essas transformações. A escala de anotação é distinta da escala geométrica.

O projeto incorporado contém valores assumidos ou de demonstração, incluindo elementos não obtidos dos desenhos de referência. As verificações visuais não constituem validação normativa nem aprovação de projeto.

Antes de uso técnico, confirmar bitola, PK, rumos, raios, transições, cotas, escala, unidades e critérios de aceitação. Comparar exemplos analíticos simples e referências de projeto, incluindo limites de intervalos e mudanças de alinhamento.

## Estrutura e desenvolvimento

- [index.html](index.html): aplicação distribuída.
- [README.md](README.md): utilização e limites.

Não há fontes de autoria separadas, manifesto de dependências ou testes externos nesta árvore. Para manutenção continuada, recuperar as fontes originais e o processo de build antes de fazer alterações extensas no JavaScript incorporado.

## Verificação

Documentação baseada na leitura de partes do artefacto em 11/11/2026. Não foram executados testes de navegador, exportações CAD ou validação dos cálculos. As funções descritas são identificadas no código, não certificadas por ensaios nesta atualização.
