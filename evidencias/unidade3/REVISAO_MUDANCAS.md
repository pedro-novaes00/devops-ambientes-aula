# Proposta de Mudança e Revisão em Dupla

## DevOps — Unidade 3

**Universidade:** Universidade Veiga de Almeida (UVA)  
**Professor:** Prof. Dr. Felipe Cordeiro

**Integrantes:**
- Pedro Henrique Novaes — 1250216570
- Willian Carvalho Velasco — 1250123808

## 1. Introdução

Nesta atividade, utilizamos Git e GitHub para organizar as alterações realizadas nos laboratórios de DevOps.

O trabalho foi desenvolvido em dupla, utilizando branches, commits e Pull Requests para registrar as mudanças, revisar os arquivos e acompanhar os resultados dos testes.

## 2. Primeira proposta — Docker

**Autor:** Willian Carvalho Velasco  
**Revisor:** Pedro Henrique Novaes  
**Pull Request:** #2

### Alteração realizada

Foi modificado o arquivo `docker/index.html`, atualizando a mensagem exibida na página do sistema de matrículas.

### Efeito esperado

Após a reconstrução da imagem Docker, a aplicação deveria apresentar o conteúdo atualizado, mantendo o funcionamento do servidor Nginx.

### Execução e verificação

Utilizamos `docker compose up --build -d` para reconstruir a imagem e iniciar o serviço.

Em seguida, executamos `curl http://localhost:8080` para verificar se a página apresentava o conteúdo atualizado.

### O que permaneceu sem alteração

O servidor continuou utilizando Nginx, e o mapeamento correto de portas permaneceu `8080:80` após os testes.

### Revisão

Pedro revisou a alteração, conferiu os resultados apresentados e registrou sua participação no PR #2, que foi integrado à branch principal.

## 3. Segunda proposta — Terraform

**Autor:** Pedro Henrique Novaes  
**Revisor:** Willian Carvalho Velasco  
**Pull Request:** #4

### Alteração realizada

Foi adicionado o arquivo `terraform/.terraform.lock.hcl`, responsável por registrar informações sobre a versão e a integridade dos provedores utilizados pelo Terraform.

### Efeito esperado

O arquivo ajuda a manter as dependências do Terraform consistentes entre diferentes ambientes de desenvolvimento.

### Execução e verificação

A alteração foi registrada em uma branch própria e enviada ao GitHub pelo PR #4.

Willian conferiu o arquivo adicionado e registrou sua análise no Pull Request.

### O que permaneceu sem alteração

O arquivo `terraform/main.tf` e as configurações dos laboratórios Docker e Ansible não foram modificados nessa proposta.

### Revisão

Willian revisou a alteração realizada pelo Pedro, registrou seu comentário no GitHub e realizou o merge na branch principal.

## 4. Atualização do ambiente Terraform

**Autor:** Willian Carvalho Velasco  
**Revisor:** Pedro Henrique Novaes  
**Branch:** `feat/terraform-versao2`

### Alteração realizada

Foi atualizado o arquivo `terraform/main.tf`, acrescentando `VERSAO=2` ao conteúdo do recurso `local_file.ambiente`.

### Efeito esperado

O Terraform deveria identificar a mudança no planejamento e atualizar o arquivo `ambiente.txt` com a nova versão.

### Execução e verificação

Executamos `terraform plan` para verificar as alterações necessárias.

Em seguida, utilizamos `terraform apply` e confirmamos que o arquivo apresentava o conteúdo esperado:

- `AMBIENTE=homologacao`
- `VERSAO=2`

Também verificamos o planejamento sem novas alterações e, ao final, removemos o recurso com `terraform destroy`.

### O que permaneceu sem alteração

A atualização modificou somente o conteúdo do recurso no `main.tf`, preservando o provedor e as configurações dos laboratórios Docker e Ansible.

### Revisão

Pedro revisou a proposta de atualização do Terraform, verificando a inclusão de `VERSAO=2`, o efeito esperado e as evidências dos testes. A revisão foi registrada no Pull Request correspondente.

## 5. Organização das evidências

Os testes realizados durante os laboratórios foram documentados com capturas de tela e explicações.

As evidências estão organizadas no diretório `evidencias/unidade3/`, incluindo os resultados dos laboratórios Docker, Terraform e Ansible.

O histórico das alterações, revisões e integrações pode ser consultado na seção de Pull Requests do repositório.

## 6. Conclusão

A atividade demonstrou a importância de registrar e revisar alterações antes de integrá-las ao projeto.

Com o uso de branches e Pull Requests, foi possível organizar as contribuições da dupla, verificar os resultados das mudanças e manter um histórico do desenvolvimento.

Os laboratórios também permitiram compreender o gerenciamento automatizado de ambientes, a identificação de falhas e a recuperação das configurações.