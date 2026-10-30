# Triagem Inteligente de Chamados

Protótipo de AI Builder para reduzir o trabalho manual de organizar solicitações de suporte. A pessoa descreve o chamado e a IA sugere uma classificação e uma resposta inicial.

## Problema de negócio

Solicitações de suporte chegam em formatos diferentes e muitas vezes sem detalhes suficientes. Isso dificulta priorizar, encaminhar e responder com consistência.

## O que foi construído

- Interface web para informar título e descrição do chamado.
- API em FastAPI que envia a solicitação a um modelo de linguagem.
- Resposta estruturada com categoria, prioridade sugerida, resumo, justificativa, resposta inicial e dados que faltam.
- Validação dos valores retornados pela IA antes de exibi-los.

A prioridade e o encaminhamento são sugestões. Uma pessoa deve revisar o resultado antes de registrar ou agir sobre o chamado.

## Executar localmente

Requer Python 3.10 ou superior e uma chave de API compatível com a API da OpenAI.

1. Crie um ambiente virtual: `python -m venv .venv`
2. Ative-o: Windows `.venv\\Scripts\\activate`; macOS/Linux `source .venv/bin/activate`
3. Instale as dependências: `pip install -r requirements.txt`
4. Copie `.env.example` para `.env` e informe `OPENAI_API_KEY`.
5. Inicie: `uvicorn app:app --reload`
6. Abra `http://127.0.0.1:8000`

`AI_MODEL` pode definir o identificador de modelo disponível na sua conta. A chave é lida pelo backend e não deve ser publicada.

## Exemplo fictício

**Título:** Não consigo acessar o e-mail  
**Descrição:** Desde esta manhã, o Outlook pede a senha repetidamente. A internet funciona e já reiniciei o computador.

## Privacidade e limites

Use apenas dados fictícios ou públicos nesta demonstração. O texto enviado é encaminhado ao provedor configurado. Não inclua senhas, dados pessoais, informações internas ou conteúdo confidencial. A resposta do modelo pode estar errada e precisa de revisão humana.

## Componentes

- `app.py`: endpoint, integração com o modelo e validação da resposta.
- `static/index.html`: formulário e apresentação do resultado.
- `requirements.txt`: dependências.
- `.env.example`: nomes das configurações necessárias, sem segredos.
