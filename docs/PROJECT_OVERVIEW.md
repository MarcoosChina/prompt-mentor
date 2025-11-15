# PROJECT_OVERVIEW.md

## 1. Visão Geral do Projeto

Este documento serve como um "Resource Kit" ou "Boilerplate Library" para o projeto **Prompt Mentor**. Ele contém os templates e modelos de arquivo essenciais que o Mentor de IA usará para guiar a criação e configuração de projetos, garantindo consistência e aderência às boas práticas de engenharia definidas no `PROJECT_INIT.md`.

---

## 2. Template Padrão de `README.md` (Para Projetos Guiados)

Este é o modelo que o Mentor usará como base para os projetos em `/guided-projects/`.

```markdown
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

```

---

## 3. Template `pyproject.toml` (Base para P0-09 a P0-14)

Este é o arquivo mais crítico para o P0. Ele define o projeto, as dependências e *todas* as ferramentas de qualidade.

```toml
[tool.poetry]
name = "prompt-mentor-cli"
version = "0.1.0"
description = "CLI Tool para interagir com o Mentor de Engenharia de Software."
authors = ["Seu Nome <seu.email@exemplo.com>"]
readme = "README.md"
license = "MIT"

[tool.poetry.dependencies]
python = "^3.8"
PyYAML = "^6.0"
rich = "^13.0"
typer = {version = "^0.9.0", extras = ["all"]}
python-dotenv = "^1.0.0"
mkdocs = "^1.5.0"

# Dependências de IA (serão adicionadas depois)
# openai = "^0.28.0"
# google-generativeai = "^0.2.0"

[tool.poetry.group.dev.dependencies]
pytest = "^7.4.0"
pytest-cov = "^4.1.0"
black = "^23.7.0"
isort = "^5.12.0"
flake8 = "^6.1.0"
bandit = "^1.7.5"
safety = "^2.3.5"

[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"

[tool.black]
line-length = 88
target-version = ['py38']

[tool.isort]
profile = "black"
line_length = 88
multi_line_output = 3
include_trailing_comma = true

[tool.flake8]
max-line-length = 88
extend-ignore = "E203"

[tool.pytest.ini_options]
minversion = "6.0"
addopts = "-ra -q --cov=cli --cov-report=term-missing"
testpaths = ["tests"]
filterwarnings = ["ignore::DeprecationWarning"]

[tool.bandit]
skips = ["B101"]
```

---

## 4. Template `prompt_config.yaml` (Base para P0-05)

```yaml
# Configuração do Mentor de IA
llm:
  provider: "openai"
  model: "gpt-4-turbo"
  api_key_env: "OPENAI_API_KEY"
  temperature: 0.3
  max_tokens: 4096

mentor_guide_file: "mentor/MENTOR_SENIOR_ENGINEERING_GUIDE.md"
logging_level: "INFO"
specializations_dir: "mentor/specializations/"
```

---

## 5. Template `.github/workflows/validate_security.yml`

```yaml
name: CI - Verificação de Segurança

on:
  push:
    branches: ["main"]
  pull_request:
    branches: ["main"]

jobs:
  security-scan:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout do código
        uses: actions/checkout@v4
      - name: Configurar Python e Poetry
        uses: actions/setup-python@v5
        with:
          python-version: '3.8'
      - name: Instalar Poetry
        uses: snok/install-poetry@v1
      - name: Instalar dependências
        run: poetry install --with dev
      - name: Rodar Bandit
        run: poetry run bandit -r . -c pyproject.toml
      - name: Rodar Safety
        run: poetry run safety check --full-report
```

---

## 6. Template `Dockerfile`

```dockerfile
FROM python:3.8-slim-buster AS builder
ENV POETRY_VERSION=1.5.1     POETRY_HOME="/opt/poetry"     POETRY_NO_INTERACTION=1     PATH="$POETRY_HOME/bin:$PATH"
RUN curl -sSL https://install.python-poetry.org | python3 -
WORKDIR /app
RUN poetry config virtualenvs.create false
COPY pyproject.toml poetry.lock ./
RUN poetry install --no-root --no-dev

FROM python:3.8-slim-buster AS final
RUN useradd --create-home --shell /bin/bash appuser
USER appuser
WORKDIR /home/appuser/app
COPY --from=builder /usr/local/lib/python3.8/site-packages /usr/local/lib/python3.8/site-packages
COPY --from=builder /usr/local/bin /usr/local/bin
COPY ./cli ./cli
ENTRYPOINT ["python", "-m", "cli.mentor_cli"]
```

---

## 7. Outros Templates

### `.env.example`

```bash
OPENAI_API_KEY="SUA_CHAVE_API_AQUI"
# GOOGLE_API_KEY=""
# LOG_LEVEL="DEBUG"
```

### `.vscode/settings.json`

```json
{
  "editor.defaultFormatter": "ms-python.black-formatter",
  "editor.formatOnSave": true,
  "python.linting.enabled": true,
  "python.linting.flake8Enabled": true,
  "python.linting.banditEnabled": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": "explicit"
  },
  "python.testing.pytestArgs": ["tests"],
  "python.testing.unittestEnabled": false,
  "python.testing.pytestEnabled": true
}
```

### `.github/PULL_REQUEST_TEMPLATE.md`

```markdown
## 1. Descrição

## 2. Tarefa(s) Relacionada(s)

- Resolve: [ID-DA-TAREFA]

## 3. Checklist de "Definition of Done" (DoD)

- [ ] **[Processo]** O PR segue o padrão de branch (`feature/ID-XX`).
- [ ] **[Processo]** O commit segue o padrão de commit semântico.
- [ ] **[Documentação]** A documentação (`README.md`, `docs/`, docstrings) foi atualizada.
- [ ] **[Código]** O código passa no Lint (`poetry run black .`, `poetry run flake8 .`).
- [ ] **[Código]** Nenhum segredo (chaves) foi "hardcoded".
- [ ] **[Testes]** Novos testes foram adicionados para cobrir as mudanças.
- [ ] **[Testes]** Todos os testes (`poetry run pytest`) passam.
- [ ] **[Testes]** A cobertura de testes está igual ou superior a 70%.
- [ ] **[Logs]** O logging necessário foi implementado.
```

---

## 8. Template de Monitoramento e Logging

Este template define uma configuração base para logging estruturado em projetos Python.

```python
# cli/logging_config.py
import logging
import sys

def setup_logger(name: str, level: str = "INFO"):
    formatter = logging.Formatter(
        '[%(asctime)s] [%(levelname)s] %(name)s: %(message)s'
    )
    handler = logging.StreamHandler(sys.stdout)
    handler.setFormatter(formatter)
    logger = logging.getLogger(name)
    logger.setLevel(level)
    logger.addHandler(handler)
    return logger
```

- Recomenda-se usar JSONLogger ou custom formatter caso o projeto escale para múltiplos ambientes (exemplo: produção e desenvolvimento).
- Adaptar chamadas de logger nos principais comandos da CLI.

---

## 9. Template de Testes de Segurança Automatizados

Diretório sugerido: `/tests/security_tests.py`

```python
import pytest
from cli.mentor_cli import process_input

@pytest.mark.parametrize("input_text", [
    "' OR 1=1 --",
    "#$%@!*&",
    "<script>alert(1)</script>"
])
def test_input_sanitization(input_text):
    # Exemplo: função process_input deve rejeitar ou tratar entradas maliciosas
    result = process_input(input_text)
    assert "error" not in result.lower()
```

- Integrar este arquivo à pipeline de CI para rodar a cada PR.

---

## 10. Template de Revisão de Política de Segurança e Atualização de Dependências

Adicionar na documentação ou agenda do projeto:

```markdown
### Política de Revisão de Segurança

- Revisar trimestralmente dependências do projeto usando `safety` e atualização via Poetry.
- Revisar e, se necessário, atualizar práticas conforme OWASP Top 10.
- Documentar decisões e atualizações em logs de auditoria internos do repositório na pasta `/docs/security-reports/`.
```

---

## 11. Template para Autenticação Segura (Plano Futuro)

```python
# cli/auth.py (esqueleto)
import jwt
import datetime

def generate_token(user_id: str, secret: str, exp_seconds: int = 3600):
    payload = {
        "user_id": user_id,
        "exp": datetime.datetime.utcnow() + datetime.timedelta(seconds=exp_seconds),
    }
    return jwt.encode(payload, secret, algorithm="HS256")

def verify_token(token: str, secret: str):
    try:
        payload = jwt.decode(token, secret, algorithms=["HS256"])
        return payload
    except jwt.ExpiredSignatureError:
        return None
    except jwt.InvalidTokenError:
        return None
```

- TODO: detalhar documentação dos fluxos de expiração/renovação e guardar segredo somente em variáveis de ambiente.

---

## 12. Template de Validação Estrita de Entrada para CLI

```python
# cli/mentor_cli.py (exemplo de uso com Pydantic)
from pydantic import BaseModel, ValidationError

class CommandInput(BaseModel):
    command: str
    argument: str

def main(args):
    try:
        data = CommandInput(command=args[0], argument=args[1])
    except ValidationError as err:
        print("Erro de validação:", err)
        return
    # continuar execução com data já validado
```

- Documentar schemas válidos conforme comandos aceitos no CLI.

---

## 13. Monitoramento e Segurança

- Incluir configuração de logging estruturado para facilitar auditorias.
- Adicionar testes específicos focados em segurança, rodados na pipeline CI.
- Definir métricas para cobertura de testes, bugs, e vulnerabilidades.
- Revisar política de segurança e dependências regularmente.

---

## 14. Processo de Deploy Seguro

- Documentar processos para rollback, backups e monitoramento pós-deploy.
- Incluir etapas de validação de segurança antes do deploy em produção.
- Automatizar deploys com ferramentas como Docker, Kubernetes, ou CI/CD.
