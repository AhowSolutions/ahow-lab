# LAB-002 - Primeiro Monitoramento do MikroTik

## Objetivo

Associar o Template oficial "MikroTik by SNMP" ao primeiro Host monitorado da Ahow Solutions.

## Resultado

✅ Comunicação SNMP estabelecida

✅ Descoberta automática das interfaces

✅ Coleta de CPU

✅ Coleta de Hardware

✅ Coleta de Firmware

✅ Coleta ICMP

✅ Primeiro gráfico disponível

## Aprendizados

Neste laboratório foi possível compreender que o Template não monitora diretamente o equipamento. Ele cria diversos Items responsáveis por consultar OIDs específicos via SNMP. Os dados coletados são armazenados no banco do Zabbix e posteriormente utilizados por Triggers, Dashboards e Grafana.
