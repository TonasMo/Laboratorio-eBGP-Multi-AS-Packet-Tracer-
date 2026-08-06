Projeto de simulação de roteamento dinâmico externo **eBGP (External BGP)** interligando 4 Sistemas Autónomos (AS 1, AS 2, AS 3 e AS 4),
numa topologia em anel com links seriais e Ethernet.

## 📐 Estrutura da Rede

- **R1 (AS 1):** Loopback `1.1.1.1/32`
- **R2 (AS 2):** Loopback `2.2.2.2/32`
- **R4 (AS 3):** Loopback `3.3.3.3/32`
- **R3 (AS 4):** Loopback `4.4.4.4/32`

### Endereçamento das Conexões
- **R1 - R2:** `10.0.0.0/30`
- **R2 - R4:** `10.0.0.8/30`
- **R4 - R3 (Link 1):** `10.0.0.12/24`
- **R4 - R3 (Link 2):** `10.0.0.16/24`
- **R3 - R1:** `150.1.1.0/24`

## ⚙️ Tecnologias Utilizadas
- Protocolo eBGP (External BGP)
- Sub-roteamento VLSM
- Anúncio de Prefixos Loopback via BGP

## 📁 Estrutura do Repositório
- `config/` - Contém as configurações CLI individuais de cada roteador (R1 a R4).
- `topology/` - Imagem da topologia do Cisco Packet Tracer.

## 🔍 Comandos de Verificação (Cisco CLI)
- `show ip bgp summary` — Verifica o estado das sessões eBGP com os vizinhos.
- `show ip bgp` — Exibe a tabela BGP com os caminhos de AS (`AS-Path`).
- `show ip route bgp` — Mostra as rotas instaladas na tabela de roteamento.
