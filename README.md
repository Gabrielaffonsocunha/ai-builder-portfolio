# AI Builder Portfolio — Gabriel Affonso

Dois protótipos de IA aplicada a tarefas reais de negócio. Cada projeto tem uma interface web, uma API Python e uma integração configurável com um modelo de linguagem.

## Projetos

| Projeto | Problema atendido | O que a IA faz |
| --- | --- | --- |
| [Triagem Inteligente de Chamados](./projetos/triagem-inteligente) | Chamados chegam com descrições variadas e precisam ser organizados rapidamente. | Sugere categoria, prioridade, resumo, resposta inicial e informações que ainda faltam. |
| [Reunião em Ações](./projetos/reuniao-em-acoes) | Anotações de reunião ficam dispersas e decisões podem não virar acompanhamento. | Organiza resumo, decisões, responsáveis, prazos e perguntas em aberto. |

## Como os protótipos usam IA

Os dois projetos enviam o texto fornecido pelo usuário a uma API compatível com a API da OpenAI e solicitam uma resposta estruturada em JSON. A saída é uma sugestão para revisão humana. A chave fica no servidor, em variável de ambiente, e não é exposta no navegador.

Os exemplos de entrada são fictícios. Não use informações pessoais, dados internos ou conteúdo confidencial.

## Executar

Cada projeto tem instruções próprias. Em resumo: crie e ative um ambiente virtual Python, instale o `requirements.txt`, copie `.env.example` para `.env`, configure uma chave de API válida e execute `uvicorn app:app --reload` dentro da pasta do projeto.

## Limites conhecidos

- Os resultados dependem do modelo e podem conter erros; confira antes de agir.
- É necessário configurar uma chave de API. O repositório não inclui chave nem oferece inferência sem credenciais.
- Os protótipos não autenticam usuários, não persistem entradas e não substituem ferramentas corporativas.
- Não foram conectados a sistemas reais nem usam dados de clientes ou colaboradores.

## Tecnologias

Python, FastAPI, HTML, CSS, JavaScript e API de modelo de linguagem.

## Autor

Gabriel Affonso Cunha — portfólio de projetos práticos para a trilha AI Builder.
