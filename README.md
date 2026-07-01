# Laboratório 01 - Reconhecimento de Rede e SSH

## Objetivo

Realizar reconhecimento de rede utilizando Nmap e analisar um serviço SSH ativo em uma máquina virtual dentro de um ambiente controlado.

## Ambiente

- Kali Linux (máquina atacante)
- Máquina virtual alvo
- VirtualBox
- Rede isolada de laboratório

## Ferramentas utilizadas

- Nmap
- SSH
- Linux

---
 Problema inicial - Conectividade da máquina virtual

Durante a preparação do laboratório foi identificado que a máquina Kali Linux não possuía acesso à rede, impedindo a atualização dos pacotes.

## Diagnóstico

Foi verificado o estado da conexão de rede e identificado que a interface da máquina virtual não estava com conectividade funcional.

## Correção aplicada

Foi ajustada a configuração de rede da máquina virtual para permitir comunicação.

Após a correção foi possível acessar a rede e continuar o laboratório.

Comandos utilizados para validação:

```bash
ping 8.8.8.8
e
sudo apt update

Resultado : A conectividade foi restaurada e o ambiente ficou pronto para execução dos testes Nmap e SSH.


# Etapa 1 - Descoberta da máquina

Foi realizada uma varredura para identificar os dispositivos ativos na rede.

Comando utilizado:

```bash
nmap -sn 192.168.x.x/24
```

Resultado:

Identificação do endereço IP da máquina alvo.

![Descoberta da rede](imagens/01-descoberta-rede.png)

---

# Etapa 2 - Análise de portas e serviços

Após identificar o alvo, foi realizada uma análise das portas abertas e serviços executando.

Comando utilizado:

```bash
nmap -sV IP_DA_MAQUINA
```

Resultado:

Foi identificado o serviço SSH ativo na porta 22.

![Análise Nmap](imagens/02-nmap-servicos.png)

---

# Etapa 3 - Conexão SSH

Foi realizada uma conexão remota utilizando o protocolo SSH.

Comando utilizado:

```bash
ssh usuario@IP_DA_MAQUINA
```

A conexão foi estabelecida com sucesso.

![Conexão SSH](imagens/03-ssh-conexao.png)

---

# Conceitos aprendidos

- O Nmap é utilizado para reconhecimento de rede e identificação de serviços.
- Portas abertas podem indicar serviços disponíveis em uma máquina.
- O SSH permite acesso remoto seguro através de criptografia.
- A porta padrão do SSH é a porta 22.
- Serviços expostos podem representar riscos caso estejam desatualizados ou configurados incorretamente.

---

# Conclusão

Neste laboratório foi possível praticar técnicas básicas de reconhecimento em redes, identificação de serviços e conexão remota utilizando SSH.

O exercício demonstra a importância de conhecer quais serviços estão ativos em uma infraestrutura e como a exposição de portas deve ser gerenciada corretamente.
