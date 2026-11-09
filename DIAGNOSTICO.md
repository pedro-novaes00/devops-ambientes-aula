# Diagnóstico do ambiente de matrículas

## Unidade 3 — DevOps

**Universidade:** Universidade Veiga de Almeida (UVA)  
**Professor:** Prof. Dr. Felipe Cordeiro

**Integrantes:**
- Pedro Henrique Novaes — 1250216570
- Willian Carvalho Velasco — 1250123808

## 1. Problemas identificados

O cenário apresenta três problemas no ambiente de um sistema fictício de matrículas.

| Problema | Consequência | Estado desejado | Evidência da correção |
|---|---|---|---|
| Versões diferentes do banco de dados | Testes podem funcionar em homologação, mas falhar em produção. | Versões compatíveis e controladas nos dois ambientes. | Comparar as versões e realizar testes funcionais. |
| Porta liberada manualmente | Pode causar diferenças de configuração e problemas de segurança. | Porta configurada e documentada no repositório. | Verificar a configuração e testar o acesso ao serviço. |
| Configuração depende de uma pessoa | A equipe pode ter dificuldades para reproduzir o ambiente. | Configuração automatizada, documentada e versionada. | Outro integrante consegue preparar e verificar o ambiente. |

## 2. Camadas afetadas

- **Banco de dados:** camadas de dados, software e configuração.
- **Porta liberada manualmente:** camadas de rede, segurança e configuração.
- **Dependência de uma pessoa:** camadas de configuração e operação.

## 3. Classificação das intervenções

- **Configuração:** alinhar as versões do banco e registrar corretamente as regras de acesso.
- **Gerenciamento:** identificar diferenças entre ambientes, revisar alterações e manter a documentação atualizada.
- **Provisionamento:** criar automaticamente os recursos necessários, quando houver necessidade.
- **Implantação:** publicar a aplicação e verificar seu funcionamento após a configuração do ambiente.

## 4. Conclusão

O diagnóstico mostrou a importância de manter os ambientes padronizados, documentados e sob controle de versão.

O uso de ferramentas de automação e a revisão das alterações pela equipe permitem reduzir erros, facilitar a reprodução do ambiente e verificar se as configurações estão funcionando corretamente.