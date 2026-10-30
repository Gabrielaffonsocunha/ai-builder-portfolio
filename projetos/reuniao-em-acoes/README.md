# Reunião em Ações

Protótipo de AI Builder para converter anotações de reunião em um resumo, decisões e itens de acompanhamento estruturados.

## Problema de negócio

Depois de uma reunião, decisões e próximos passos podem ficar espalhados em anotações livres. Isso aumenta o risco de tarefas sem responsável ou prazo passarem despercebidas.

## O que foi construído

- Interface para colar anotações fictícias.
- API em FastAPI integrada a um modelo de linguagem.
- Extração estruturada de resumo, decisões, ações, responsáveis, prazos, prioridade e perguntas em aberto.
- Regra explícita para não inventar responsáveis nem prazos ausentes: o campo aparece como “Não informado”.

O resultado ajuda a organizar o acompanhamento, mas precisa de conferência dos participantes antes de ser tratado como ata oficial.

## Executar localmente

Requer Python 3.10 ou superior e uma chave de API compatível com a API da OpenAI.

1. Crie um ambiente virtual: `python -m venv .venv`
2. Ative-o: Windows `.venv\\Scripts\\activate`; macOS/Linux `source .venv/bin/activate`
3. Instale as dependências: `pip install -r requirements.txt`
4. Copie `.env.example` para `.env` e informe `OPENAI_API_KEY`.
5. Inicie: `uvicorn app:app --reload`
6. Abra `http://127.0.0.1:8000`

`AI_MODEL` pode definir o identificador de modelo disponível na sua conta. Não publique o arquivo `.env`.

## Exemplo fictício

“Marina vai enviar a primeira versão do painel até sexta. O time vai revisar na próxima reunião. Ainda precisamos decidir quem fará a documentação.”

## Privacidade e limites

Use apenas dados fictícios ou públicos. O texto é encaminhado ao provedor configurado. Não cole transcrições reais, dados pessoais, informações internas ou conteúdo confidencial. A IA pode interpretar incorretamente uma anotação; valide o resultado com os participantes.

## Componentes

- `app.py`: endpoint, integração com o modelo e validação.
- `static/index.html`: formulário e apresentação dos itens extraídos.
- `requirements.txt`: dependências.
- `.env.example`: nomes das configurações necessárias, sem segredos.
