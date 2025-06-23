Django API com Docker e GitHub Actions

Este projeto é uma API Django simples, empacotada com Docker, e com CI/CD automatizado usando GitHub Actions.  
A imagem final é enviada automaticamente para o Docker Hub em cada `push` na branch `main`.

---

 Tecnologias Utilizadas

- [Django](https://www.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [Gunicorn](https://gunicorn.org/)
- [Docker](https://www.docker.com/)
- [GitHub Actions](https://docs.github.com/en/actions)

---

 Como Executar Localmente com Docker

 Pré-requisitos:
- Docker instalado na máquina

 Passos:


git clone https://github.com/ANAVIMIZA/django-api-docker-pipeline.git
cd django-api-docker-pipeline
docker build -t django-api .
docker run -p 8000:8000 django-api
Acesse em: http://localhost:8000/status/


A imagem é publicada automaticamente em:
 https://hub.docker.com/r/anavimiza/django-api-docker-pipeline

Sempre que você fizer push na branch main, o GitHub Actions:

Faz login no Docker Hub

Constrói a imagem

Publica no Docker Hub com a tag latest


Estrutura do Projeto
bash
Copiar
Editar
django-api-docker-pipeline/
├── core/                 # Projeto Django
├── status/               # App com endpoint /status/
├── Dockerfile            # Define a imagem Docker
├── docker-compose.yml    # (opcional) Execução local
├── requirements.txt      # Dependências da aplicação
└── .github/workflows/    # CI/CD com GitHub Actions

Pipeline (CI/CD)
O arquivo .github/workflows/docker-build.yml define o pipeline que:

Aciona em push na main

Faz build da imagem Docker

Envia para o Docker Hub

 Teste de Endpoint
Com o contêiner rodando:

bash
Copiar
Editar
curl http://localhost:8000/status/
Resposta esperada:

json
Copiar
Editar
{"status": "ok"}

Requisitos (requirements.txt)
nginx
Copiar
Editar
django
djangorestframework
gunicorn

 Autor
GitHub: @ANAVIMIZA
Docker Hub: anavimiza

