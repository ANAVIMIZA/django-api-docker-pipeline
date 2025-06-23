# Django API com Docker e GitHub Actions

Este projeto é uma API simples com Django REST Framework que retorna o status do sistema.

## 🔧 Tecnologias

- Django
- Django REST Framework
- Gunicorn
- Docker
- GitHub Actions

## 🚀 Executar localmente

```bash
docker-compose up --build
```

Acesse: [http://localhost:8000/status/](http://localhost:8000/status/)

## 🐳 Docker Hub

A imagem é publicada automaticamente em:  
[https://hub.docker.com/r/<seu usuário>/django-api-docker-pipeline](https://hub.docker.com/r/<seu usuário>/django-api-docker-pipeline)

## 🔄 CI/CD com GitHub Actions

Push na branch `main` aciona a pipeline para build e push da imagem Docker.

## 📂 Estrutura

- `/core`: Projeto Django
- `/status`: App com rota `/status/`
- `Dockerfile`: Criação da imagem
- `docker-compose.yml`: Execução local
- `.github/workflows`: Pipeline CI/CD
