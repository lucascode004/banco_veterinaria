# Banco de Dados - Clínica Veterinária

Projeto de banco de dados desenvolvido para a clínica veterinária Melhor Amigo.

## Estrutura do projeto

```text
banco_veterinaria/
├── docs/
│   ├── Lógico_1.brM3
│   ├── Lógico_2.brM3
│   └── Lógico_3.brM3
│
├── scripts/
│   ├── site.sql
│   ├── adm.sql
│   └── contabil.sql
│
└── README.md

* Execução dos scripts

Os scripts devem ser executados na seguinte ordem:

1. scripts/site.sql
2. scripts/adm.sql
3. scripts/contabil.sql

Essa ordem é necessária porque existem chaves estrangeiras entre tabelas de diferentes schemas.

* Modelos lógicos

Os modelos lógicos foram desenvolvidos utilizando o brModelo:

- `docs/Lógico_1.brM3` — modelo lógico do schema `site`.
- `docs/Lógico_2.brM3` — modelo lógico do schema `adm`.
- `docs/Lógico_3.brM3` — modelo lógico do schema `contabil`.

* Views

Foram criadas views para facilitar consultas frequentes:

* Schema `site`

- `site.clientes_pets`: utilizada pela equipe do site para consultar clientes e seus respectivos pets.
- `site.produto_catalogo`: utilizada pela equipe do site para visualizar os produtos disponíveis no catálogo.

* Schema `adm`

- `adm.lista_clientes`: utilizada pela equipe administrativa para consultar os dados dos clientes.
- `adm.relatorio_funcionarios`: utilizada pela equipe administrativa para consultar informações dos funcionários.

* Constraints

Foram adicionadas constraints `CHECK` para garantir a integridade dos dados:

- `chk_pet_idade`: impede idade de pet menor que zero.
- `chk_pet_peso`: impede peso de pet menor ou igual a zero.
- `chk_pedido_status`: permite apenas os status definidos para os pedidos.

Também foram revisadas as regras de `ON DELETE` e `ON UPDATE` das chaves estrangeiras, buscando preservar os registros importantes e manter a integridade dos relacionamentos.
