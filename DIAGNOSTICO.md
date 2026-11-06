# Diagnóstico do ambiente de matrículas

## Unidade 3 — DevOps

### 1. Problemas identificados

| Problema | Consequência | Estado desejado | Evidência da correção |
|---|---|---|---|
| Versões diferentes do banco em homologação e produção | Testes podem passar em homologação e falhar em produção devido à incompatibilidade. | Versões das dependências relevantes compatíveis e controladas. | Comparação das versões e testes funcionais de matrícula. |
| Porta liberada manualmente | Desvio de configuração (drift), com possível exposição indevida do serviço. | Porta e regras de acesso documentadas, revisadas e aplicadas conforme a configuração aprovada. | Comparação das regras reais com as definidas no repositório e teste de acesso. |
| Configuração depende de uma pessoa | Dificuldade para reproduzir o ambiente na ausência do responsável. | Configuração automatizada, documentada e versionada no GitHub. | Outro integrante consegue preparar e verificar o ambiente com base nos arquivos do repositório. |

### 2. Classificação das intervenções

- **Configuração:** alinhar versões e ajustar as regras da porta.
- **Gerenciamento:** identificar o drift, revisar as alterações e manter as configurações atualizadas.
- **Provisionamento:** disponibilizar os recursos necessários ao ambiente, caso precisem ser criados.
- **Implantação:** publicar a aplicação e testar o funcionamento após a preparação do ambiente.

### 3. Conclusão

Os problemas mostram a importância de manter os ambientes de homologação e produção sob controle de versão, automatizar configurações e verificar os resultados das mudanças. A documentação e a revisão em equipe reduzem a dependência de uma única pessoa.