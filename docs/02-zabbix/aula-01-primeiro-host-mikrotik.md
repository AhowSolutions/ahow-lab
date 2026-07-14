# Aula 01 - Primeiro Host MikroTik

## Objetivo

Configurar a comunicação entre o Zabbix Server e um MikroTik utilizando o protocolo SNMP.

---

## Ambiente do Laboratório

### Servidor Zabbix

| Informação | Valor |
|------------|-------|
| Sistema Operacional | Debian 13 |
| IP | 192.168.10.28 |
| Zabbix | 7.0.28 |

### MikroTik

| Informação | Valor |
|------------|-------|
| Equipamento | RB750Gr3 (hEX) |
| RouterOS | 7.23.1 |
| IP | 192.168.10.1 |

---

## Configuração realizada

### SNMP

Status

```
Habilitado
```

Community

```
ahow-monitor
```

Rede autorizada

```
192.168.10.0/27
```

---

## Testes realizados

### Ping

Resultado

```
OK
```

### SNMP Walk

Comando utilizado

```bash
snmpwalk -v2c -c ahow-monitor 192.168.10.1 1.3.6.1.2.1.1
```

Resultado

```
Comunicação realizada com sucesso.
```

Foi possível visualizar:

- Nome do equipamento
- Versão do RouterOS
- Uptime
- Informações do equipamento

---

## Host Group criado

```
AHOW - Network
```

Objetivo

Organizar os equipamentos de rede da infraestrutura da Ahow.

---

## Conceitos aprendidos

- Host Groups
- Host
- SNMP
- Community
- OID
- SNMP Walk
- Organização do ambiente

---

## Próximos passos

- Criar o primeiro Host no Zabbix
- Importar o Template Oficial do MikroTik
- Monitorar CPU
- Monitorar Memória
- Monitorar Interfaces
- Criar Dashboard no Grafana

---

## Observações

Foi confirmado que a comunicação SNMP entre o servidor Debian e o MikroTik está funcionando corretamente.

A disponibilidade SNMP permaneceu em cinza devido à ausência de um Template associado ao Host.

Essa configuração será realizada na próxima etapa.
