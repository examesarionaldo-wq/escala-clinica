# Gerador de Escalas da Clínica

Aplicativo gratuito em Streamlit para gerar escalas de trabalho da clínica veterinária.

## Arquivos

- `app.py`: aplicativo completo.
- `requirements.txt`: dependências instaladas automaticamente pelo Streamlit.

## Publicação gratuita

1. Crie uma conta gratuita no GitHub.
2. Crie um novo repositório, por exemplo `escala-clinica`.
3. Envie `app.py` e `requirements.txt` para a raiz do repositório.
4. Entre no Streamlit Community Cloud usando a conta do GitHub.
5. Clique em **Create app**.
6. Escolha o repositório, a branch `main` e o arquivo `app.py`.
7. Clique em **Deploy**.

## Uso

1. Escolha o mês e o ano.
2. Informe feriados, folgas e noites fixas de Nicolle.
3. Clique em **Gerar escala**.
4. Confira o resumo e baixe o Excel.

## Observação sobre armazenamento

Esta versão não usa banco de dados. As configurações existem durante a sessão e podem ser baixadas em JSON. Isso mantém o projeto gratuito e simples.


## Regra de equilíbrio

Ana e Danielle recebem o mesmo número de plantões diurnos e noturnos sempre que matematicamente possível. Quando o total disponível for ímpar ou houver restrições incompatíveis, o aplicativo minimiza a diferença entre elas. Os plantões diurnos incluem os turnos regulares, domingos e feriados.

## Regra obrigatória de dobradinha

Quando Ana ou Danielle trabalhar no plantão noturno das 19h às 07h e também precisar trabalhar no dia seguinte, o único turno permitido será das 07h às 16h. Assim, a jornada começa às 19h e termina às 16h do dia seguinte. O sistema proíbe o turno das 10h às 19h e o plantão de domingo/feriado das 07h às 19h após uma noite.
