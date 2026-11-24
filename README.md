# Plataforma Municipal

Protótipo front-end em HTML, CSS e JavaScript sem dependências externas.

## Arquivos

- `index.html`: encaminha para o painel inicial.
- Cada pasta de tela contém seu próprio `index.html`, por exemplo `dashboard/index.html`, `vistorias/index.html` e `vistorias-nova/index.html`.
- `css/styles.css`: estilos responsivos para smartphone, tablet e desktop.
- `js/app.js`: navegação, telas, formulários, filtros e dados demonstrativos.
- `data/config.js`: município, usuário, talões e checklist editáveis.
- Cada rota tem uma pasta própria com `index.html`, incluindo agenda, criação de processos, usuários, detalhes e histórico.
- Os módulos operacionais também têm índices independentes: `transportes`, `ait-nova`, `ait-consultar`, `medidas`, telas Novo/Consultar para FRD, FRV, VA, OA, Termo e TCO, `boat-novo`, `boat-consultar`, `operacoes`, `of-novo`, `of-consultar`, `of-qrcode`, `rastreamento`, `ocorrencia-nova` e `ocorrencia-consultar`.

## Personalização

Edite `data/config.js` para alterar o município, o usuário ativo, as opções de talão e os itens do checklist. Os atributos `data-tag` do HTML identificam campos associados a dados do sistema, por exemplo `municipio.nome` e `usuario.nome`.

## Uso

Sirva a pasta por um servidor web local e abra `index.html` ou entre diretamente em uma tela, como `vistorias-nova/index.html`. Por exemplo, com Python instalado, abra um terminal nesta pasta e execute:

```text
py -m http.server 8000
```

Depois acesse `http://localhost:8000`. Usar uma origem comum mantém a navegação entre arquivos e o armazenamento local do navegador. Os registros ficam no navegador; este protótipo ainda não possui API, autenticação ou banco de dados.

## Recursos locais implementados

- A tela de fiscalização, vistoria, recolhimento e apreensão permite desenhar assinaturas usando toque ou mouse.
- Fotos da câmera/galeria e documentos PDF/Word podem ser adicionados, visualizados e removidos antes de salvar; ficam vinculados ao registro no navegador.
- As configurações podem ser editadas e gravadas localmente. Município e checklist também passam a aparecer nos campos correspondentes.
- Anexos têm limites de tamanho e quantidade para reduzir falhas por falta de espaço no navegador.
- A AIT libera os campos após a escolha da modalidade. Ocorrências liberam o formulário após selecionar um dos dez tipos; Medidas Administrativas abrem a etapa Novo/Consultar após a escolha do documento.
- AIT, medidas, BOAT, operações e ocorrências podem ser registrados e consultados no armazenamento local do navegador. A consulta de veículos usa os registros locais e informa quando não há localização recente disponível.

## Limites

- Os dados ficam apenas no navegador e no aparelho usados para registrar. Para sincronizar entre usuários ou dispositivos, será necessário conectar uma API e banco de dados com autenticação e armazenamento de arquivos.
- Agenda, relatórios e histórico ainda incluem conteúdo demonstrativo.
