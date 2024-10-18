# Ollama no Kubernetes: Guia Completo

## Introdução

Este repositório fornece um guia passo a passo para implantar o Ollama, um poderoso framework para executar Large Language Models (LLMs), em um ambiente Kubernetes. Com este guia, você poderá facilmente criar e gerenciar seus próprios LLMs personalizados em um cluster Kubernetes.

## Pré-requisitos

* **Cluster Kubernetes:** Um cluster Kubernetes em funcionamento.
* **kubectl:** A ferramenta de linha de comando do Kubernetes instalada e configurada.
* **Docker:** Docker instalado e configurado para criar as imagens do Ollama.
* **Um modelo LLM:** Você precisará de um modelo LLM pré-treinado ou treinado por você. Neste guia, utilizaremos o modelo `mxbai-embed-large` como exemplo.

## Instalação

1. **Clone este repositório:**

```bash
git clone [URL inválido removido]
```

2. **Edite o arquivo deploy.yaml:**

* Escolha o modelo: Substitua mxbai-embed-large pelo nome do modelo que você deseja utilizar.
* Configure os recursos: Ajuste os recursos de CPU e memória de acordo com as necessidades do seu modelo.

3. **Implante o Ollama:**

```Bash
kubectl apply -f deploy.yaml
```

4. **Exponha o serviço:**
```Bash
kubectl apply -f service.yaml
```

## Uso

Para interagir com o Ollama, você pode utilizar a interface de linha de comando ou criar uma aplicação que se conecte ao serviço exposto.

Exemplo de interação via linha de comando:

```Bash
# Obtenha o nome do serviço
kubectl get services

# Envie uma solicitação para o serviço
curl http://seu-servico:porta -d '{"prompt": "Olá, mundo!"}'
```

## Personalização

* Modelos: Você pode utilizar qualquer modelo LLM compatível com o Ollama.
* Recursos: Ajuste os recursos de CPU e memória para otimizar o desempenho do seu modelo.
* Configurações: Explore as opções de configuração do Ollama para personalizar o comportamento do seu modelo.

## Referências

* Documentação oficial do Ollama: https://ollama.com/
* Documentação do Kubernetes: https://kubernetes.io/docs/
