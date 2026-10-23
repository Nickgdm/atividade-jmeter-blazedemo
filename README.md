# Teste de Performance com Apache JMeter — BlazeDemo

Projeto de teste de performance para o site de demonstração BlazeDemo, utilizando Apache JMeter e uma massa de dados CSV para parametrizar a origem e o destino das buscas de voos.

## Objetivos

- Configurar requisições HTTP para o cenário de busca de voos;
- Parametrizar os dados de origem e destino com CSV;
- Exercitar o sistema com usuários virtuais concorrentes;
- Praticar a configuração e execução de um plano de teste de performance.

## Tecnologias

- Apache JMeter 5.6.3 (versão indicada no arquivo do plano)
- HTTP/HTTPS
- CSV para dados de teste

## Arquivos

- `Test Plan.jmx` — plano de teste do JMeter. A configuração atual define 50 usuários virtuais, ramp-up de 180 segundos e duração de 300 segundos.
- `massa_dados.csv` — dados de origem e destino utilizados para parametrizar as requisições.

## Pré-requisitos

- Java compatível com a versão do JMeter instalada;
- Apache JMeter 5.6.3 ou versão compatível;
- Acesso à internet para alcançar o site de demonstração.

## Como executar

1. Baixe e instale o Apache JMeter.
2. Clone este repositório.
3. Abra `Test Plan.jmx` no JMeter.
4. Na configuração **CSV Data Set Config**, ajuste o campo **Filename** para apontar para o arquivo `massa_dados.csv` dentro do diretório local do projeto. O plano versionado contém um caminho absoluto de uma máquina específica, que não funcionará em outros computadores.
5. Confira se as variáveis `origem` e `destino` correspondem aos cabeçalhos do CSV.
6. Execute primeiro com uma carga reduzida para validar a configuração e só depois utilize os 50 usuários virtuais definidos no plano.

Também é possível executar em modo não gráfico após validar o plano:

```bash
jmeter -n -t "Test Plan.jmx" -l resultados.jtl
```

## Cuidados ao interpretar resultados

A configuração de carga não representa, por si só, um resultado de performance. Registre métricas como tempo de resposta, taxa de erro e throughput durante a execução. Execute testes de carga apenas em ambientes para os quais você tenha autorização.

## Contexto

Projeto educacional desenvolvido para praticar conceitos de teste de performance com o Apache JMeter.
