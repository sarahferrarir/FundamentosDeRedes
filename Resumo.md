# Resumo das aulas 1 - 8

## **1. Introdução e Conceitos Fundamentais de Redes**

### **1.1. O que é uma Rede?**

Uma rede de computadores é um sistema que permite o compartilhamento de recursos e serviços, como arquivos, impressoras, aplicações e informações. Ela é composta por dispositivos finais (hosts), dispositivos intermediários e meios de transmissão. 

- **Dispositivos Finais (ETD - Equipamento Terminal de Dados)**: São a origem ou o destino das mensagens na rede, como computadores, smartphones e servidores.
- **Dispositivos Intermediários (ECD - Equipamento de Comunicação de Dados)**: Conectam os dispositivos finais entre si ou a outras redes. Exemplos incluem roteadores, switches, access points (APs) e firewalls.
- **Meios de Transmissão**: A mídia pela qual os dados viajam. Pode ser por cabos de cobre (sinais elétricos), fibra óptica (pulsos de luz) ou sem fio (ondas eletromagnéticas).

### **1.2. Modelos de Referência OSI e TCP/IP**

São modelos conceituais que descrevem as funções necessárias para a comunicação em rede. O modelo mais utilizado na prática é o **TCP/IP**, mas o **OSI** é fundamental para entender os conceitos, pois detalha mais as funções.

| Modelo OSI (7 Camadas) | Modelo TCP/IP (4 Camadas) | Funções Principais |
| --- | --- | --- |
| **7. Aplicação** | **4. Aplicação** | Fornece interface com o usuário e a aplicação. Engloba as funções das camadas de Sessão, Apresentação e Aplicação do modelo OSI. |
| **6. Apresentação** |  **4. Aplicação**  | Formatação, compressão e criptografia de dados.  |
| **5. Sessão** | **4. Aplicação**   | Cria, mantém e gerencia diálogos entre as aplicações. |
| **4. Transporte** | **3. Transporte** | Responsável pela segmentação, sequenciamento e remontagem dos dados. Usa os protocolos TCP e UDP. |
| **3. Rede** | **2. Internet** | Endereçamento lógico (IP), roteamento de pacotes entre redes diferentes e comutação de pacotes.  |
| **2. Enlace** | **1. Acesso à Rede** | Endereçamento físico (MAC), controle de acesso ao meio e encapsulamento de quadros.  |
| **1. Física** | **1. Acesso à Rede** | Transmissão e recepção de bits pelo meio físico. Define características elétricas e mecânicas.  |

## **2. Camada de Acesso à Rede (Camadas 1 e 2)**

### **2.1. Endereçamento MAC (Camada 2)**

O **endereço MAC** (Media Access Control) é um endereço físico de 48 bits, exclusivo para cada placa de rede (NIC). Ele é usado para identificar dispositivos dentro de um mesmo enlace de rede local. 

- **Tipos de Endereço MAC**:
    - **Unicast**: Transmissão de um para um.
    - **Broadcast**: Transmissão de um para todos os dispositivos no mesmo segmento de rede. O endereço de destino é **FF:FF:FF:FF:FF:FF**.
    - **Multicast**: Transmissão de um para um grupo específico de dispositivos. O endereço de destino depende do protocolo, como `01-00-5E` para pacotes IPv4 ou `33-33` para IPv6.

### **2.2. O Quadro Ethernet**

É a unidade de dados da camada de enlace. Ele encapsula o pacote da camada de rede (IPv4 ou IPv6) e adiciona um cabeçalho e um trailer. 

- **Campos Importantes**:
    - **Endereços MAC de Origem e Destino**: Identificam os dispositivos físicos na rede local.
    - **Tipo/Tamanho**: Indica qual protocolo da camada superior (ex: IPv4, IPv6, ARP) está encapsulado nos dados.
    - **Dados**: Contém o pacote da camada superior.
    - **FCS (Frame Check Sequence)**: Usado para detecção de erros. O receptor calcula um CRC e compara com o valor no campo; se não coincidir, o quadro é descartado.

### **2.3. Topologias e Meios de Transmissão**

As **topologias físicas** definem o layout da rede19. As mais comuns são:

- **Ponto a Ponto**: Conexão dedicada entre dois dispositivos.
- **Barra**: Todos os nós compartilham um único meio. Transmissões são recebidas por todos.
- **Anel**: Dispositivos conectados em série, com dados fluindo unidirecionalmente.
- **Estrela/Árvore**: Cada dispositivo se conecta a um ponto central (como um switch). É a topologia mais comum em redes modernas.

Os **meios de transmissão** mais comuns são:

- **Cabos de Cobre (UTP)**: Baixo custo e fácil instalação. O entrançamento dos pares de fios ajuda a mitigar a diafonia (crosstalk).
- **Fibra Óptica**: Transmite dados via pulsos de luz, sendo imune a interferências eletromagnéticas. Ideal para longas distâncias e alta largura de banda.
- **Sem Fio (Wireless)**: Usa ondas de rádio, ideal para mobilidade. Padrões como
    
    **Wi-Fi (802.11)** e **Bluetooth (802.15)**. 
    

## **3. Camada de Internet (Camada 3)**

### **3.1. Roteamento e Comutação de Pacotes**

O **roteamento** é o processo de encaminhar pacotes entre redes distintas. Os roteadores utilizam tabelas de roteamento para escolher o melhor caminho para os pacotes. A **comutação de pacotes** é a técnica de dividir a mensagem em unidades menores (pacotes) para serem encaminhadas individualmente. Isso aumenta a tolerância a falhas, pois os pacotes podem seguir rotas alternativas. 

### **3.2. Protocolo IP (Internet Protocol)**

O IP é o principal protocolo da camada de Internet. Ele encapsula segmentos da camada de transporte em **pacotes IP** e os endereça para entrega de ponta a ponta. 

- **IPv4**: Endereço de 32 bits, representado em quatro octetos decimais separados por pontos (ex: 192.168.1.1). A escassez de endereços IPv4 públicos levou à criação do NAT (Network Address Translation).
- **IPv6**: Endereço de 128 bits, usando uma notação hexadecimal com oito "hextetos" (ex: `2001:0db8:0000:1111:0000:0000:0000:0200`). Ele resolve o problema de escassez de endereços do IPv4 e tem um cabeçalho mais simples, facilitando o processamento.

### **3.3. Endereçamento IPv4: Máscara de Sub-rede e Subnetting**

O endereço IPv4 é composto por uma parte de rede e uma parte de host. A **máscara de sub-rede** é usada para diferenciar essas duas partes. 

- O **endereço de rede** é obtido por um `AND` lógico bit a bit entre o endereço IP e a máscara de sub-rede. Ele tem todos os bits da porção do host como zero.
- O **endereço de broadcast** tem todos os bits da porção do host como um. É usado para se comunicar com todos os dispositivos na rede.
- Os **endereços de host** são os endereços que podem ser atribuídos a dispositivos, exceto o endereço de rede e o de broadcast.

**Subnetting**: Dividir uma rede em sub-redes menores. Isso melhora a eficiência, segurança e o gerenciamento do tráfego. 

- **Notação CIDR**: Usada para simplificar a representação da máscara de sub-rede, como `/24` para `255.255.255.0`.
- **VLSM (Variable Length Subnet Mask)**: Permite usar diferentes máscaras de sub-rede em uma mesma rede para otimizar o uso de endereços, evitando desperdício.

### **3.4. Protocolos Auxiliares (ICMP e ARP)**

- **ICMP (Internet Control Message Protocol)**: Usado para troca de mensagens de controle e para dar feedback sobre erros na entrega de pacotes. O comando `ping` utiliza o ICMP para testar a conectividade.
- **ARP (Address Resolution Protocol)**: Funciona no IPv4 para mapear dinamicamente um endereço IP a um endereço MAC correspondente. O dispositivo consulta sua tabela ARP e, se não encontrar o MAC, envia uma requisição ARP broadcast.

## **4. Camada de Transporte (Camada 4)**

A camada de transporte é responsável por gerenciar a comunicação entre aplicações em hosts diferentes. Ela usa dois protocolos principais: TCP e UDP.

### **4.1. TCP (Transmission Control Protocol)**

É um protocolo **orientado à conexão**, que garante a entrega confiável, controle de fluxo e de erros. É comparado a um serviço de carta registrada, pois o remetente recebe a confirmação de que a mensagem foi entregue. 

- **Three-Way Handshake**: Processo de 3 etapas para estabelecer uma conexão confiável: SYN, SYN-ACK, ACK.
- **Segmentação e Remontagem**: Divide os dados em segmentos e usa números de sequência para remontá-los na ordem correta no destino.
- **Controle de Erro**: Usa números de confirmação (ACK) para garantir o recebimento dos segmentos.
- **Controle de Fluxo**: Usa o campo "tamanho da janela" para regular a quantidade de dados que o receptor pode receber de uma vez.

### **4.2. UDP (User Datagram Protocol)**

É um protocolo **não orientado à conexão**, mais simples e rápido que o TCP. Não oferece garantia de entrega, controle de fluxo ou de erro. É ideal para aplicações que toleram perdas de dados, mas exigem baixa latência, como streaming de vídeo e VoIP. 

### **4.3. Portas e Sockets**

As portas (ou "endereços de serviço") são números que identificam as aplicações em um host. 

- **Portas Bem-Conhecidas (0-1023)**: Usadas para serviços de servidor comuns (ex: HTTP 80, HTTPS 443, FTP 21, DNS 53).
- **Portas Registradas (1024-49151)**: Atribuídas a aplicações específicas por solicitação.
- **Portas Dinâmicas (49152-65535)**: Atribuídas dinamicamente pelo cliente para identificar uma conversa.

Um **socket** é a combinação do endereço IP e o número da porta, identificando uma comunicação única. Ex:

`192.168.10.20:80`. 

### **5. Camada de Aplicação (Camada 5, 6 e 7)**

A camada de aplicação fornece os serviços de rede para os usuários finais. 

- **DNS (Domain Name System)**: Converte nomes de domínio (ex: `www.google.com`) em endereços IP. A consulta DNS usa o protocolo UDP na porta 53 para clientes, e TCP na porta 53 para sincronização entre servidores.
- **DHCP (Dynamic Host Configuration Protocol)**: Atribui dinamicamente endereços IP e outras configurações de rede (máscara de sub-rede, gateway, DNS) aos dispositivos.
    - **DHCPv4**: Usa broadcast na porta UDP 67/68 para a descoberta e requisição de endereços.
    - **DHCPv6 / SLAAC**: No IPv6, os hosts podem obter endereços de forma dinâmica via DHCPv6 ou por autoconfiguração sem estado (SLAAC), usando mensagens ICMPv6.
- **Serviços de E-mail**:
    - **SMTP (Simple Mail Transfer Protocol)**: Usado para envio de e-mails entre clientes e servidores, e entre servidores.
    - **POP3 (Post Office Protocol)** e **IMAP4 (Internet Message Access Protocol)**: Usados para os clientes recuperarem e-mails do servidor. POP3 baixa e remove as mensagens, enquanto IMAP4 mantém as mensagens no servidor.
- **Serviços Web**:
    - **HTTP (Hypertext Transfer Protocol)**: Protocolo de requisição e resposta usado para a navegação na web. Usa a porta TCP 80.
    - **HTTPS**: Versão segura do HTTP que usa criptografia SSL/TLS, operando na porta TCP 443.
