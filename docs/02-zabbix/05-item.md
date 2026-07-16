# Item

## Objetivo

Compreender o conceito de Item no Zabbix e entender sua importância para a coleta de dados, geração de gráficos e criação de alertas.

---

## O que é?

Um Item é a menor unidade de coleta de dados do Zabbix.

Ele representa uma informação específica que será monitorada em um Host, como uso de CPU, memória, uptime, interfaces de rede, temperatura, espaço em disco ou qualquer outra métrica disponível.

Em outras palavras, um Item é a "pergunta" que o Zabbix faz ao equipamento monitorado.

---

## Para que serve?

O Item é responsável por informar ao Zabbix:

- Qual informação deve ser coletada.
- Como essa informação será coletada (SNMP, Zabbix Agent, ICMP, HTTP, SSH, entre outros).
- Com qual frequência essa coleta será realizada.

Sem um Item, o Zabbix não possui dados para armazenar, gerar gráficos ou disparar alertas.

---

## Como funciona?

Quando um Template é associado a um Host, todos os Items presentes nesse Template passam a fazer parte do monitoramento desse equipamento.

O Zabbix Server consulta periodicamente cada Item utilizando o método configurado.

Exemplo do fluxo de funcionamento:

Host → Template → Items → Coleta de Dados → Banco de Dados → Gráficos → Triggers → Dashboard → Alertas

---

## Exemplo na Ahow

Host:

RTR-AHOW-LAB-01

Template:

AHOW - MikroTik Base

Items:

- Uso de CPU
- Memória Livre
- Uptime
- Interface WAN
- Interface LAN
- Tráfego da Ether1
- Temperatura
- Versão do RouterOS

Após associar o Template ao Host, o Zabbix começa automaticamente a coletar essas informações conforme o intervalo definido para cada Item.

---

## Exemplo prático

Imagine que desejamos monitorar o uso da CPU de um MikroTik.

O Item será responsável por perguntar periodicamente ao equipamento:

"Qual é o uso atual da CPU?"

O MikroTik responde, por exemplo:

CPU = 3%

Essa informação é armazenada no banco de dados do Zabbix e poderá ser utilizada posteriormente para:

- Construção de gráficos.
- Criação de Triggers.
- Dashboards no Grafana.
- Histórico de utilização.

---
## Exemplo Prático 2

Host:
MikroTik hEX

Item:
System Name

Método de coleta:
SNMP

OID:
1.3.6.1.2.1.1.5.0

Valor retornado:
ahow

Intervalo:
15 minutos

Objetivo:
Identificar o nome configurado no equipamento e preencher automaticamente o inventário do host.
---

## Boas práticas

- Utilizar Templates sempre que possível.
- Nomear os Items de forma padronizada.
- Definir intervalos de coleta adequados para cada tipo de informação.
- Evitar criar Items duplicados.
- Monitorar apenas informações realmente úteis para a operação.

---

## Erros comuns

- Criar vários Items para a mesma informação.
- Configurar intervalos de coleta muito curtos sem necessidade.
- Esquecer de associar o Template ao Host.
- Utilizar OIDs incorretos em monitoramentos SNMP.
- Criar Items sem um objetivo claro.

---

## Resumo

- Um Item representa uma única informação monitorada.
- Cada Item coleta apenas um tipo de dado.
- Os Items pertencem aos Templates.
- Quando um Template é associado a um Host, todos os seus Items passam a monitorar esse equipamento.
- Sem Items não existem gráficos, históricos, Triggers ou Dashboards.

---

## Como eu explicaria isso para um cliente?

Imagine um check-up médico.

Cada exame solicitado pelo médico representa um Item.

- Pressão arterial.
- Temperatura.
- Frequência cardíaca.
- Glicemia.

Cada exame coleta apenas uma informação.

Depois que todos os exames são realizados, o médico consegue avaliar a saúde do paciente.

No Zabbix acontece exatamente o mesmo.

Cada Item coleta uma informação do equipamento.

Com todas essas informações reunidas, o sistema consegue gerar gráficos, detectar problemas e emitir alertas antes que uma falha afete o ambiente.

---

## O que aprendemos nesta aula?

✅ O Item é a menor unidade de monitoramento do Zabbix.

✅ Cada Item coleta apenas uma informação.

✅ Os Items são definidos dentro dos Templates.

✅ O Zabbix Server é responsável por realizar a coleta.

✅ Os dados coletados alimentam gráficos, Triggers, dashboards e históricos.

---

## Próxima aula

**Trigger**

Vamos entender como o Zabbix transforma dados coletados em alertas inteligentes.
