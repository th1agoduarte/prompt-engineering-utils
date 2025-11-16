# Classificação geral de documentos

# Relevantes

| Documento | Categoria | Características |
| --- | --- | --- |
| **PRD (Product Requirements Document)** | **Produto**  | Liga visão de negócio à execução técnica. Define propósito, valor e métricas. É leve, iterativo e coescrito por PMs e tech leads. |
| **HLD (High-Level Design)** | **Design e Arquitetura**  | Mostra a arquitetura geral, componentes e integrações. É o alicerce técnico de toda a documentação moderna. |
| **FDD (Feature Design Doc)** | **Design e Arquitetura** | Define o “como implementar” de uma feature. É o sucessor direto do FRD, mas focado em clareza e execução técnica. |
| **ADR (Architecture Decision Record)** | **Design e Arquitetura** | Leve e rastreável. Registra decisões arquiteturais ao longo do tempo. É o padrão ouro de governança técnica moderna. |
| **RFC (Request for Comments)** | **Design e Arquitetura** | Promove discussões técnicas assíncronas. Amplamente usado em times maduros e open source. |
| **Runbooks / Playbooks** | **Operacional** | Essenciais em DevOps e SRE. Documentam operação, reinício de serviços e resposta a incidentes. |
| **Engineering Guidelines** | **Conhecimento e Referência** | Centralizam boas práticas de engenharia (code style, CI/CD, segurança, etc.). |
| **Security Design Doc** | **Conhecimento e Referência** | Define padrões de segurança, autenticação e threat modeling. |
| **Modelos C4 (Context, Container, Component, Code)** | **Design e Arquitetura** | Tornaram-se o padrão visual moderno para comunicação técnica. Simples, claros e versionáveis. |

# Emergentes / Modernos

| Documento | Categoria | Observação |
| --- | --- | --- |
| **AI Design Docs / Prompt Specs** | **Design e Arquitetura** | Nova fronteira de documentação técnica para agentes, LLMs e fluxos de IA. |
| **Observability Docs (SLIs, SLOs, métricas)** | **Operacional** | Indispensáveis no DevOps moderno. Ligam métricas, logs e tracing aos SLOs. |
| **Evaluation Docs (AI/LLM testing)** | **Conhecimento e Referência** | Novos padrões para medir precisão, custo e performance em pipelines de IA. |

# Secundários

| Documento | Categoria | Observação |
| --- | --- | --- |
| **LLD (Low-Level Design)** | **Design e Arquitetura** | Útil em sistemas críticos (concorrência, performance, algoritmos). Em times ágeis, o código e ADRs cumprem esse papel. |
| **Infrastructure Design Doc** | **Infraestrutura** | Ainda necessário para ambientes complexos, mas boa parte vive hoje em IaC (Terraform, Helm, etc.). |
| **User Stories e Epics** | **Produto** | Relevantes para gestão e produto, mas não substituem PRD/FDD. |
| **CI/CD Documentation** | **Infraestrutura** | Mantém rastreabilidade dos pipelines e deploys. Muitas vezes integrada ao código. |

# Documentos com relevância menor ou herança Waterfall (RUP, processos antigos)