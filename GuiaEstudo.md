# Guia de Estudo para Ap1
### **1. Modelos OSI e TCP/IP**

A prova pode exigir que você saiba a correlação entre as camadas dos dois modelos. 
Entenda que a camada de "Acesso à Rede" do TCP/IP corresponde às camadas "Física" e de "Enlace" do modelo OSI. Além disso, a camada de "Aplicação" do TCP/IP agrupa as funções das camadas de "Sessão", "Apresentação" e "Aplicação" do OSI.

### **2. Camada de Rede (Camada de Internet)**

- **Encapsulamento e Desencapsulamento**: Lembre-se do processo de como os dados são encapsulados, com a adição de cabeçalhos em cada camada, e como são desencapsulados no destino. Entenda que a PDU (unidade de dados do protocolo) de uma camada se torna "dados" para a camada inferior.
- **Protocolo IP**: Saiba as diferenças entre **IPv4** (32 bits) e **IPv6** (128 bits). Fique atento aos campos do cabeçalho IPv4, como **TTL** (Time to Live) e **Protocolo**, que indicam o tempo de vida do pacote e o protocolo da camada de transporte, respectivamente.
- **Sub-redes**: Para a prova, é crucial saber como calcular o **endereço de rede** e o **endereço de broadcast** a partir de um endereço IP e uma máscara de sub-rede. O conceito de VLSM para otimizar o uso de endereços também é importante.
- **ARP e ICMP**: O **ARP** é essencial para a resolução de endereços, mapeando um IP a um MAC na rede local. O
    
    **ICMP** é usado para mensagens de controle, como o `ping` para testar conectividade e o `tracert` para rastrear rotas.
    

### **3. Camada de Transporte**

- **TCP vs. UDP**: A distinção é fundamental. O **TCP** é orientado à conexão, confiável, e usa o "three-way handshake" para estabelecer a comunicação. O **UDP** não é confiável e é mais rápido, ideal para aplicações que toleram perda de dados.
- **Portas**: Entenda o conceito de portas como endereços de serviço para aplicações. Lembre-se dos grupos de portas ( **bem-conhecidas**, **registradas** e **dinâmicas**) e de exemplos de portas para serviços comuns, como HTTP (80) e HTTPS (443).

### **4. Camada de Enlace e Física**

- **Switches**: Saiba como um switch de Camada 2 aprende e encaminha quadros. Ele usa o endereço MAC de origem para popular a sua tabela MAC e o endereço MAC de destino para tomar decisões de encaminhamento.
