# Pipeline CI com GitHub Actions

## 1. Introdução

Este projeto implementa um pipeline de Integração Contínua (CI) utilizando GitHub Actions com runner auto-hospedado no Ubuntu via WSL2.

## 2. Ambiente Utilizado

- **Sistema Operacional:** Ubuntu 26.04 (WSL2 no Windows)
- **Python:** 3.14.4
- **Git:** 2.53.0
- **GitHub Actions Runner:** 2.334.0
- **Runner tipo:** Self-hosted

## 3. Estrutura do Repositório

devops-ci-activity/
├── calculadora.py
├── test_calculadora.py
├── requirements.txt
├── screenshots/
└── .github/
    └── workflows/
        └── ci.yml

## 4. Desenvolvimento

### Parte 1 — Preparação do Servidor Ubuntu

![Evidência 1](screenshots/evidencia1-01-versoes-python-git.png)
![Evidência 2](screenshots/evidencia1-02-ambiente-preparado.png)

### Parte 2 — Estrutura do Repositório

![Evidência 3](screenshots/evidencia2-01-estrutura-repositorio.png)

### Parte 3 — Pipeline GitHub Actions

![Evidência 4](screenshots/evidencia3-01-pipeline-verde.png)
![Evidência 5](screenshots/evidencia3-02-pipeline-detalhes.png)
![Evidência 6](screenshots/evidencia3-03-testes-passando.png)

### Parte 4 — Runner Self-Hosted

![Evidência 7](screenshots/evidencia4-01-configuracao-runner.png)
![Evidência 8](screenshots/evidencia4-02-runner-configurado.png)
![Evidência 9](screenshots/evidencia4-03-runner-ativo.png)
![Evidência 10](screenshots/evidencia4-04-pipeline-self-hosted-verde.png)

## 5. Problemas Encontrados

| Problema | Solução |
|----------|---------|
| Python 3.10 não disponível no Ubuntu 26.04 | Removido o step setup-python, usado Python do sistema |
| pip bloqueado por ambiente gerenciado | Criado virtualenv com python3-venv |
| python3-venv não instalado | Instalado via sudo apt install python3.14-venv |

## 6. Conclusão

O pipeline CI foi implementado com sucesso, executando automaticamente a cada git push, rodando 5 testes com pytest e utilizando runner self-hosted no Ubuntu via WSL2.
