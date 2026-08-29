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

- O primeiro domingo pode ser atribuído a Ana, Danielle ou Suzana.

### Regra de dobradinha
Ana e Danielle nunca podem trabalhar no turno diurno e iniciar o plantão noturno no mesmo dia. A única dobradinha permitida começa às 19h e termina às 16h do dia seguinte: noite 19h–07h seguida do turno 07h–16h.

### Regra de folga após dobradinha de sexta para sábado

Quando Ana ou Danielle fizer a dobradinha iniciada na sexta-feira às 19h e encerrada no sábado às 16h, ela deverá obrigatoriamente folgar o domingo inteiro seguinte. O sistema bloqueia tanto o turno diurno de domingo (07h–19h) quanto o plantão noturno de domingo (19h–07h).

### Distribuição ao longo do mês
- Ana e Danielle continuam com o total mensal de plantões diurnos e noturnos igual ou o mais próximo possível.
- O aplicativo agora também busca equilíbrio dentro de cada semana, evitando concentrar muitos diurnos de uma veterinária em uma semana e muitos noturnos na semana seguinte.
- Sequências longas do mesmo tipo de plantão são penalizadas para que os dias fiquem mais intercalados ao longo do mês.
- Essa é uma regra preferencial forte: pode ser flexibilizada quando folgas, indisponibilidades, domingos, feriados ou noites fixas tornarem a distribuição ideal impossível.


## Ajuste de dobradinhas

As dobradinhas de Ana e Danielle são fortemente penalizadas pelo otimizador e só devem ser usadas quando necessárias. A regra de distribuição semanal não pode criar dobradinhas apenas para melhorar o equilíbrio visual da escala. A única dobradinha permitida continua sendo Noite 19h–07h + Dia 07h–16h do dia seguinte.


### Regra obrigatória nova
A dobradinha de Ana e Danielle é permitida somente de sexta-feira à noite para sábado no turno das 07h às 16h. Em qualquer outro dia da semana, o aplicativo proíbe a sequência noite + manhã do dia seguinte.
