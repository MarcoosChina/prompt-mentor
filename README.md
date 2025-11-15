# Prompt Mentor: Engenharia de Software e Projetos

<p align="center">
  <img alt="CI Status" src="https://github.com/tiagoeduardobr/prompt-mentor/actions/workflows/validate_security.yml/badge.svg">
  <img alt="Code Coverage" src="https://img.shields.io/badge/coverage-0%25-red?style=flat-square">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-blue?style=flat-square">
  <img alt="Python Version" src="https://img.shields.io/badge/python-3.8%2B-blueviolet?style=flat-square">
  <img alt="Poetry" src="https://img.shields.io/badge/poetry-gerenciamento-darkgreen?style=flat-square">
</p>

## 1. Descrição

 O **Prompt Mentor** é um framework open-source de engenharia de prompt que simula um **mentor sênior de engenharia de software**.
 Seu objetivo é transformar o aprendizado técnico em um processo orientado a projetos, focado em **boas práticas, segurança, testes e metodologia de engenharia real**, capacitando desenvolvedores a construir portfólios de nível profissional.

## 2. Tecnologias Utilizadas (Tech Stack)

- **Backend:** Python 3.8+, FastAPI (futuro), Typer (CLI)
- **LLM Providers:** OpenAI GPT, Google Generative AI
- **Gerenciamento de Dependências:** Poetry
- **Testes:** Pytest, Pytest-Cov
- **Qualidade:** Black, Flake8, iSort, Bandit, Safety
- **Versionamento:** Git/GitHub
- **CI/CD:** GitHub Actions
- **Documentação:** MkDocs

## 3. Como Executar (Configuração Local)

### Pré-requisitos

- Python 3.8+
- Poetry (Gerenciador de dependências)
- Conta em provedor LLM (OpenAI ou Google) para API keys

### Passos

1 Clone o repositório:

```bash
   git clone https://github.com/tiagoeduardobr/prompt-mentor.git
   cd prompt-mentor
```

2 Crie seu arquivo `.env` (use o `.env.example` como base):

```bash
   cp .env.example .env
```

   _Obs: Preencha as variáveis no `.env` com suas chaves API (ex: OPENAI_API_KEY)._

3 Instale as dependências com Poetry:

```bash
   poetry install
```

4 Ative o ambiente virtual do Poetry:

```bash
   poetry shell
```

5 (Futuro: quando houver servidor) Inicie a aplicação:

```bash
  # Exemplo futuro: uvicorn app.main:app --reload
  poetry run python -c "print('Mentor CLI pronto para uso')"
```

## 4. Como Rodar os Testes

```bash
   # Dentro do ambiente (poetry shell)
   pytest
```

Para ver o relatório de cobertura de testes:

```bash
   pytest --cov
```

## 5. Funcionalidades Principais

- Simulação de mentor sênior para guiar projetos full-stack
- Foco em boas práticas, segurança e qualidade de código
- Suporte a múltiplos provedores LLM
- CLI robusta com Typer
- Testes automatizados e CI/CD

## 6. Licença

Este projeto é distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 7. Contribuição

Contribuições são bem-vindas! Veja o `CONTRIBUTING.md` para guias de configuração e desenvolvimento.

## 8. Status do Projeto

Este projeto está em **desenvolvimento ativo (Fase P0/P1)**. A fundação de qualidade, testes e CI/CD está sendo construída, com adições recentes em segurança (monitoramento, autenticação JWT e validação CLI) e novos TODOs para reforçar qualidade e conformidade OWASP.

Para detalhes completos sobre o backlog e o roadmap, veja o `PROJECT_INIT.md`.

## 9. Roadmap

- **Fase 1 (P0):** Fundação com guia, config e estrutura.
- **Fase 2 (P1):** Expansão com specializations e testes.
- **Fase 3 (P2):** Integração com CLI e workflows.
- **Fase 4 (P3):** Educação com projetos guiados.

## 10. Suporte

Para dúvidas ou suporte, abra uma issue no GitHub ou veja o `PROJECT_INIT.md`.

---

_Este README segue o template padrão do projeto para consistência._

## Configuração Inicial

- Clone o repositório e certifique-se de que o .gitignore está configurado para ignorar arquivos sensíveis.

## 📜 Licença

Este projeto é distribuído sob a Licença MIT. Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.
