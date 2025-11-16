# Update README

Você é um assistente especializado em manter documentação de repositórios atualizada e bem organizada.

## Objetivo

Atualizar o arquivo README.md do repositório com links para todos os documentos e prompts disponíveis, organizados por categorias de forma clara e navegável.

## Instruções

1. **Escanear o repositório** para identificar:
   - Todos os arquivos de prompt (`.md`) na pasta `prompts/`
   - Todos os documentos de exemplo (`.md`) na pasta `Exemple/`
   - Todos os comandos do Claude Code (`.md`) na pasta `.claude/commands/`

2. **Categorizar os arquivos** encontrados:
   - **Prompts de Engenharia**: Prompts prontos para uso em diferentes contextos
   - **Exemplos de Documentação**: PRDs, especificações e outros documentos de exemplo
   - **Comandos Claude Code**: Comandos personalizados disponíveis no repositório

3. **Estruturar o README.md** seguindo este formato:

```markdown
# Prompt Engineering Utils

Coleção de prompts, templates e utilitários para engenharia de prompts e documentação técnica.

## 📋 Índice

- [Prompts de Engenharia](#prompts-de-engenharia)
- [Exemplos de Documentação](#exemplos-de-documentação)
- [Comandos Claude Code](#comandos-claude-code)

## 🎯 Prompts de Engenharia

Prompts prontos para uso em diferentes contextos de desenvolvimento e documentação.

[Lista de prompts com links e descrições breves]

## 📚 Exemplos de Documentação

Exemplos práticos de documentação técnica, PRDs e especificações.

[Lista de exemplos com links e descrições breves]

## ⚙️ Comandos Claude Code

Comandos personalizados disponíveis para uso com Claude Code.

[Lista de comandos com links e descrições breves]

## 🚀 Como Usar

[Instruções de uso]

## 📝 Contribuindo

[Diretrizes de contribuição]
```

4. **Gerar descrições automáticas**:
   - Para cada arquivo, extraia o título ou primeiras linhas para criar uma descrição breve
   - Use links relativos do repositório para facilitar navegação
   - Mantenha ordem alfabética dentro de cada categoria

5. **Regras importantes**:
   - Use links relativos (ex: `[Arquivo](./pasta/arquivo.md)`)
   - Adicione emojis apenas nos títulos principais de categoria
   - Mantenha descrições concisas (máximo 2 linhas)
   - Se o README.md já existir, preserve seções customizadas que não sejam as categorias principais
   - Ordene os itens alfabeticamente dentro de cada categoria

6. **Após atualizar o README**:
   - Mostre um resumo do que foi adicionado/atualizado
   - Liste quantos itens foram encontrados em cada categoria
   - Sugira ao usuário revisar o README antes de commitar

## Formato de Saída

Para cada item listado no README, use este formato:

```markdown
### [Nome do Documento](./caminho/relativo/arquivo.md)

Breve descrição extraída do conteúdo do arquivo (1-2 linhas).
```

## Exemplo de Execução

Ao executar este comando, você deve:
1. Ler todos os arquivos nas pastas relevantes
2. Criar ou atualizar o README.md
3. Organizar os links por categoria
4. Mostrar resumo das alterações
