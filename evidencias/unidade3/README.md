# Evidências dos Laboratórios — DevOps Unidade 3

**Universidade:** Universidade Veiga de Almeida (UVA)

**Professor:** Prof. Dr. Felipe Cordeiro

**Integrantes:**
- Pedro Henrique Novaes — 1250216570
- Willian Carvalho Velasco — 1250123808

## 1. Mudança aplicada

![Mudança aplicada](ansible-alteracao-aplicada.png)

O playbook Ansible foi atualizado para incluir `VERSAO=2` no arquivo `ambiente.txt`. Após a execução, o resultado foi `changed=1` e `failed=0`. A leitura do arquivo confirmou que a alteração foi aplicada corretamente.

## 2. Repetição sem mudança

![Idempotência](ansible-idempotencia.png)

Executamos o mesmo playbook novamente, sem modificar a configuração. O resultado foi `changed=0` e `failed=0`, indicando que o arquivo já estava conforme o esperado e nenhuma alteração adicional foi necessária. Esse comportamento demonstra a idempotência do Ansible.

## 3. Falha controlada

Para simular uma falha, alteramos o caminho de destino no arquivo `ansible/ambiente.yml` para uma pasta inexistente.

**Linha com erro:**

```yaml
dest: "{{ playbook_dir }}/pasta-inexistente/ambiente.txt"
```

![Falha controlada](ansible-falha.png)

**Sintoma observado:** o Ansible apresentou `failed=1` e uma mensagem informando que o diretório de destino não existia.

**Causa identificada:** a propriedade `dest` apontava para uma pasta que não havia sido criada, impedindo a gravação do arquivo.

## 4. Correção e recuperação

Para corrigir o problema, restauramos o caminho original no playbook.

**Linha corrigida:**

```yaml
dest: "{{ playbook_dir }}/ambiente.txt"
```

![Recuperação](ansible-recuperacao.png)

Após a correção, executamos o playbook novamente. O resultado foi `failed=0` e `changed=0`, confirmando que a execução voltou a funcionar e que o arquivo já estava no estado esperado.

A leitura de `ambiente.txt` confirmou o conteúdo:

```text
AMBIENTE=homologacao
VERSAO=2
```

Assim, conseguimos reproduzir a falha, identificar sua causa, corrigir a configuração e verificar a recuperação do ambiente.
