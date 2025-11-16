# Prompt Engineering Utils

A collection of utilities and templates for improving my daily work in prompt engineering. Includes reusable prompts, structured patterns, guidelines, and helper tools to streamline LLM development, automate workflows, and maintain consistency across AI projects.

## 📋 Índice

- [Prompts de Engenharia](#-prompts-de-engenharia)
- [Exemplos de Documentação](#-exemplos-de-documentação)
- [Comandos Claude Code](#%EF%B8%8F-comandos-claude-code)
- [Como Usar](#-como-usar)

## 🎯 Prompts de Engenharia

Prompts prontos para uso em diferentes contextos de desenvolvimento e documentação.

### [Entrevista para Gerar PRD de Feature](./prompts/PRD%20de%20Feature/Entrevista_para_Gerar_PRD_para_desenvolvimento_de_Feature.md)

Prompt estruturado para conduzir entrevista interativa e gerar um PRD (Product Requirements Document) completo e acionável. O assistente guia o usuário através de perguntas objetivas, captura requisitos funcionais e não funcionais, arquitetura, riscos e critérios de aceitação. Ao final, gera o PRD em formato Markdown padronizado e opcionalmente em JSON estruturado.

## 📚 Exemplos de Documentação

Exemplos práticos de documentação técnica, PRDs e especificações demonstrando boas práticas.

### [Classificação Geral de Documentos](./Exemple/classificao.md)

Guia de referência classificando tipos de documentação técnica por categoria e relevância. Inclui documentos modernos (PRD, HLD, FDD, ADR, RFC), documentos operacionais (Runbooks, Playbooks) e documentos legados ou em desuso.

### [Exemplo: Catálogo de eCommerce](./Exemple/docs/prd/Exemplo%20de%20PRD%20para%20Feature%20%28Cat%C3%A1logo%20de%20eCommerce%29.md)

PRD completo demonstrando a documentação de uma feature de catálogo de produtos para e-commerce. Inclui gestão de produtos, SKUs, variações, preço, estoque, APIs de leitura e painel administrativo. Exemplo prático de como documentar requisitos de negócio complexos, integrações e critérios de aceitação.

### [Exemplo: Rate Limiter](./Exemple/docs/prd/Exemplo%20para%20Feature%20%28Rate%20Limiter%29.md)

PRD demonstrando a documentação de um sistema de Rate Limiter centralizado. Implementado como SDK em Go com suporte a Redis Cluster e modo in-memory. Exemplo de como documentar componentes de infraestrutura crítica, requisitos não funcionais e estratégias de resiliência.

## ⚙️ Comandos Claude Code

Comandos personalizados disponíveis para uso com Claude Code CLI.

### [/commit](./claude/commands/commit.md)

Comando para criar commits convencionais seguindo o padrão Conventional Commits. Analisa automaticamente as mudanças no repositório, determina o tipo apropriado (feat, fix, docs, etc.) e gera mensagens de commit claras e profissionais com descrição e corpo explicativo.

### [/update-readme](./claude/commands/update-readme.md)

Comando para atualizar automaticamente o README.md do repositório. Escaneia as pastas de prompts, exemplos e comandos, organiza por categorias e gera links com descrições extraídas do conteúdo dos arquivos.

## 🚀 Como Usar

### Prompts

1. Navegue até a pasta `prompts/`
2. Escolha o prompt adequado ao seu caso de uso
3. Copie o conteúdo e use com seu LLM preferido (Claude, ChatGPT, etc.)

### Exemplos

1. Navegue até a pasta `Exemple/`
2. Consulte os exemplos de PRDs e documentação técnica
3. Use como referência para seus próprios documentos

### Comandos Claude Code

Se você está usando [Claude Code](https://github.com/anthropics/claude-code):

1. Os comandos na pasta `.claude/commands/` ficam automaticamente disponíveis
2. Use `/commit` para criar commits convencionais
3. Use `/update-readme` para atualizar este README automaticamente

## 📝 Estrutura do Repositório

```
.
├── .claude/
│   └── commands/          # Comandos personalizados do Claude Code
├── prompts/               # Prompts reutilizáveis organizados por categoria
│   └── PRD de Feature/    # Prompts para geração de PRDs
├── Exemple/               # Exemplos de documentação
│   └── docs/
│       └── prd/          # Exemplos de PRDs completos
└── README.md             # Este arquivo
```

## 🤝 Contribuindo

Sinta-se à vontade para adicionar novos prompts, exemplos ou comandos que possam ser úteis para engenharia de prompts e documentação técnica.

---

**Última atualização:** 2025-11-16
