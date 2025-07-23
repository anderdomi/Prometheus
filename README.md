Curso Devops 2
# Prometheus

# Observabilidade:

Usando arquivos de log podemos buscar visibilidade . No cenário de serviços independentes e desacoplados, fica difícil ter controle. O erro pode estar vindo de um serviço anterior por exemplo.

Por isso usamos a observabilidade para ter total controle sobre o que está acontecendo na sua aplicação antes de um cliente te avise.

Antes de qualquer coisa você vai poder ver gargalos que possam estar acontecendo no seu cliente te ligue ou sua aplicação fique fora,

Para iso use os 3 pilares.

Métricas: São medições numéricas de dados relacionadosa elementos do seu software ou da sua infraestrutura. Normalmente são números e relacionados a uma linha temporal.

- Consumo de CPU.
- Quantidade de requisições.
- Consumo de memória
- Quantidade de instâncias rodando no momento.

Logs: São registros relacionados a eventos que aconteceram em um determinado momento na apliação ou na infraestrutura. Normalmente os eventos são textuais e acompanham dados estrututrados ao contexto do evento. Muito usado para debug da aplicação.
- Quais tipos de dados você armazena?
- Cuidado com dados da LGPD.

Trace: Rastreamento do fluxo de eventos de uma requisição entre os processos transitados. Enquanto o log foca no fluxo de eventos de um determinado processo, o traccing analisa todo o percurso para uma análise mais detalhada do comportamento do fluxo em si.


Usaremos ferramentas 100% opensource num cluster kubernetes.
[ferramentas](./img/observabilidade.png)

# prometheus

Implementando coleta de métricas. Metrificando dados númericos. Podemos coletar métricas de sistema ou de negócios.

[metricas](./img/metricas.png)

Métrica         não é       log. 
- Dados numericos           - Dados textuais
- Gráficos                  - Mensagens de erro
- Agregações                - Informação
- Perfomance                - Buscáveis

Metricas tipo COUNTER: sempre vai acrecentando até que seja reiniciado.
Metrica tipo GAUGESe: aumenta e diminuir o valor
Metrica tipo HISTOGRAM E SUMMARY: baseado em gráfico

Para isso usaremos o prometheus: Ideal para métricas de sistema.
Entenda a estrutura de coleta e armazenamento de dados da ferramenta.
Aula: Métricas e monitoramento com Prometheus
Existem ferramentas com suporte nativos e existem ferramentas com exporter para que seja possível a coleta.
Usaremos push gateway para processo de curta duração.
Usaremos alertas para notificação com regras, com Alert Manager.

[Full](./img/estrutura.png)

# Instalando Prometheus no docker.

- Arquivo docker-compose.yml
Configure o prometheus:
- Arquivo prometheus.yml
Colete as métricas do mongodb usando o exporter.
- Arqvuivo docker-compose.yml e prometheus.yml
