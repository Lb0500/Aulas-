# Atividade Avaliativa 04 — Cadastro de Loja em C

**Entrega:** 16/11  
**Tema:** Algoritmos de ordenação, manipulação de arquivos, estruturas de dados e ponteiros.

## Objetivo

Desenvolver um programa em linguagem C para gerenciar o cadastro de produtos de uma loja, armazenando os dados em arquivo de texto e oferecendo operações de cadastro, consulta, alteração, exclusão, ordenação e exportação para CSV.

## Tabela de dados inicial

| ID | Produto | Categoria | Preço (R$) | Quantidade | Fornecedor |
|---:|---|---|---:|---:|---|
| 1 | Camiseta Básica | Vestuário | 49,90 | 30 | Moda Brasil |
| 2 | Mouse Óptico USB | Informática | 59,99 | 15 | TecnoShop |
| 3 | Shampoo 300ml | Higiene Pessoal | 22,50 | 40 | Beleza Pura |
| 4 | Café 500g | Alimentos | 18,00 | 25 | Grãos do Sul |

## Funcionalidades obrigatórias

- Gerar IDs automaticamente, de forma incremental.
- Impedir o cadastro de produtos com nomes duplicados.
- Verificar se há IDs duplicados durante a inserção.
- Criar e cadastrar produtos.
- Listar os produtos em formato de tabela.
- Alterar e excluir produtos.
- Buscar produtos por nome ou categoria.
- Comparar nomes e categorias sem diferenciar letras maiúsculas e minúsculas (*case-insensitive*).
- Ordenar por nome em ordem crescente (A–Z) e decrescente (Z–A).
- Ordenar por preço do menor para o maior e do maior para o menor.
- Exportar os dados para um arquivo CSV, separando os campos por vírgula.
- Usar um vetor de estruturas, por exemplo `Produto lista[]`.
- Utilizar o algoritmo Bubble Sort para ordenar os produtos.
- Exibir listas ordenadas sem modificar a ordem dos dados salvos no arquivo.

## Estrutura sugerida

A estrutura `Produto` pode conter os seguintes campos:

```c
typedef struct {
    int id;
    char nome[50];
    char categoria[50];
    float preco;
    int quantidade;
    char fornecedor[50];
} Produto;
```

Os tamanhos dos campos de texto são limitados. Podem ser aumentados caso seja necessário armazenar nomes, categorias ou fornecedores maiores.

## Arquivos e segurança dos dados

Os produtos devem ser armazenados em um arquivo de texto. Ao alterar ou excluir um registro, o programa deve:

1. Ler os dados do arquivo original.
2. Criar um arquivo temporário com os dados atualizados.
3. Fechar os arquivos corretamente.
4. Substituir o arquivo original pelo temporário após a gravação bem-sucedida.

Essa técnica ajuda a reduzir o risco de perda ou corrupção dos dados durante alterações e exclusões. O programa também deve verificar erros ao abrir, ler, gravar e substituir arquivos.

## Ordenação com Bubble Sort

O Bubble Sort compara elementos vizinhos e troca suas posições quando estão fora da ordem desejada. O programa deve implementar as quatro opções de ordenação solicitadas. A ordenação deve ocorrer no vetor carregado em memória, sem regravar o arquivo original apenas para exibir os resultados.

## Comentários no código

Adicionar comentários explicativos ao longo do código, esclarecendo a finalidade das variáveis, estruturas, funções, ponteiros, operações com arquivos, buscas e comparações do Bubble Sort.

## Sugestão de menu

1. Cadastrar produto
2. Listar produtos
3. Alterar produto
4. Excluir produto
5. Buscar por nome
6. Buscar por categoria
7. Ordenar por nome (A–Z)
8. Ordenar por nome (Z–A)
9. Ordenar por preço (menor → maior)
10. Ordenar por preço (maior → menor)
11. Exportar para CSV
0. Sair

## Observações

- O ID deve ser gerado pelo programa; o usuário não precisa digitá-lo.
- Antes de cadastrar, verificar se já existe produto com o mesmo nome, ignorando diferenças entre maiúsculas e minúsculas.
- A geração do próximo ID deve considerar os IDs já armazenados no arquivo para evitar repetição após reiniciar o programa.
- Ao exportar para CSV, considerar que textos podem conter vírgulas; se necessário, colocar esses campos entre aspas e tratar aspas internas.
- O projeto deve ser testado com cadastro, busca, alteração, exclusão, ordenação e exportação.

## Planos de aula de referência

Planos de aula 8, 9, 11 e 12.
