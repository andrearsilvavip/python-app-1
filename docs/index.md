# python-app-1

Aplicação simples em Flask para exibir informações do servidor e realizar health check.

## Funcionalidades

- Endpoint `/api/v1/details`: Retorna o horário atual, hostname do servidor e uma mensagem de teste.
- Endpoint `/api/v1/healthz`: Retorna o status de saúde da aplicação.

## Como executar localmente

1. Instale as dependências:
   ```sh
   pip install -r requirements.txt
   ```

2. Execute a aplicação:
   ```sh
   python src/app.py
   ```

3. Acesse os endpoints:
   - [http://python-app-1-dev.test.com/api/v1/details](http://python-app-1-dev:5000/api/v1/details)
   - [http://python-app-1-dev.test.com/api/v1/healthz](http://python-app-1-dev:5000/api/v1/healthz)

## Docker

Para rodar via Docker:

```sh
docker build -t python-app-1 .
docker run -p python-app-1-dev.test.com:5000python-app-1
```

## Kubernetes

Arquivos de configuração para deploy no Kubernetes estão na pasta `k8s/`:
- `deploy.yaml`: Deployment da aplicação
- `service.yaml`: Service para expor a aplicação
- `ingress.yaml`: Ingress para acesso externo

## Helm Chart

O Helm chart está disponível em `charts/python-app-1/` para facilitar o deploy e gerenciamento.

## Integração com Backstage

O arquivo [`catalog-info.yaml`](catalog-info.yaml) permite registrar o serviço no Backstage para observabilidade e gerenciamento.

## Autor

- [andrearsilva](https://github.com/andrearsilva)