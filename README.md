# 🧠 Trabalho Mininet – Topologia Linear com 6 Switches

## 🎯 Objetivo
O objetivo deste trabalho é criar e analisar uma **topologia linear com 6 switches** utilizando o **Mininet**, explorando comandos básicos de configuração, inspeção de rede, testes de conectividade e desempenho.

---

## ⚙️ Etapas Realizadas

### 1️⃣ Criação da Topologia
A topologia foi criada via linha de comando do Mininet com:
```bash
sudo mn --topo linear,6 --link tc,bw=25 --mac
``` 
## 2️⃣ Inspeção das Interfaces e Endereços

Dentro da CLI do Mininet (mininet>), foram utilizados os seguintes comandos:

net          # Exibe conexões entre hosts e switches
dump         # Mostra IP, MAC e interfaces de cada nó
h1 ifconfig  -a # Detalha as interfaces do host h1
s1 ifconfig  -a # Detalha as interfaces de s1


Esses comandos permitiram visualizar informações das interfaces, IPs e portas.

###3️⃣ Teste de Conectividade

Para validar a comunicação entre os nós, foi utilizado:

pingall

O resultado esperado é 0% de perda de pacotes, indicando conectividade total entre os hosts.

###4️⃣ Testes de Desempenho com Iperf

Foi configurado o h1 como servidor TCP (porta 5555) e o h2 como cliente, com teste de 15 segundos e relatório por segundo:

Servidor:

iperf3 -c 10.0.0.1 -p 5555 -i 1 -t 15


Cliente:

iperf -s -p 5555


O teste apresentou medições de banda a cada segundo e um relatório final com a taxa média de transferência (~25 Mbps, conforme definido).
