# Laboratório 03: Instalar o Ubuntu na máquina virtual

**10.º TDS · Sistemas Operativos · UC02829: Instalar, configurar e parametrizar sistemas operativos**

| | |
| --- | --- |
| Equipa | ____ |
| Aluno A | ________________________________ |
| Aluno B | ________________________________ |
| Data | ____ / ____ / ______ |
| Organização | Trabalho a pares |
| Duração | 90 + 45 min |
| Onde | Bancada de SO → **Lab 03 · Instalar Ubuntu** |

## O pedido do cliente

No Lab 02 a equipa criou a VM e confirmou que ela arranca a partir da ISO do Ubuntu 24.04. O cliente pede agora que o sistema seja **instalado** e entregue pronto a usar, cumprindo os requisitos abaixo e o requisito específico da equipa.

**Requisitos comuns a todas as equipas**

- [ ] Idioma Português e teclado Português
- [ ] Fuso horário Lisboa (Europe/Lisbon)
- [ ] Nome do computador `ubu-eqNN` (NN = número da equipa)
- [ ] Nome de utilizador em minúsculas e palavra-passe com 8 ou mais caracteres, inventada para a aula
- [ ] Instalação concluída, VM a arrancar a partir do disco e sessão iniciada

> **Aviso:** a VM e os dados são simulados. Numa instalação real, confirmem sempre o disco de destino e façam uma cópia de segurança antes de alterar partições.

## Cenários das equipas

| Equipa | VM (simulada) | Requisito específico | Problema para investigar |
| --- | --- | --- | --- |
| 01 | 3 GB RAM · 2 CPU · 25 GB · UEFI · NAT | Sem partição swap dedicada | «Um colega diz que, sem uma partição swap, o Ubuntu não arranca.» |
| 02 | 4 GB · 2 CPU · 25 GB · UEFI · NAT | Partição / com pelo menos 20 GB | «Foi proposto dar só 6 GB à partição / para poupar espaço no SSD.» |
| 03 | 4 GB · 2 CPU · 30 GB · UEFI · NAT | Instalação manual com partição EFI FAT32 ≥ 0,5 GB em /boot/efi | «Um colega quer apagar a partição EFI porque é pequena e não serve para nada.» |
| 04 | 4 GB · 2 CPU · 90 GB (Windows 11 já instalado + 30 GB livres) · UEFI | Windows 11 preservado e menu de arranque com os dois sistemas | «O cliente pergunta se escolher Apagar o disco e instalar o Ubuntu é mais rápido e seguro.» |
| 05 | 2 GB · 1 CPU · 25 GB · **BIOS** · NAT | Seleção predefinida de aplicações | «Recomendam a seleção alargada de aplicações para ficar já tudo instalado.» |
| 06 | 4 GB · 2 CPU · 40 GB **dinâmico** · UEFI | Instalação manual com /home separada (EFI, / e /home) | «Um colega diz que a partição /home separada ocupa logo o espaço todo no SSD físico.» |
| 07 | 4 GB · 2 CPU · 30 GB · UEFI · **rede interna** | Instalação sem transferências adicionais | «Um aluno insiste em ligar a VM à Internet durante a instalação para descarregar codecs e drivers.» |
| 08 | 4 GB · 2 CPU · 30 GB · UEFI · NAT | ISO removida e VM a arrancar do disco | «O responsável diz que é normal a VM voltar a mostrar o instalador depois de reiniciar.» |

## 1. Rever os conceitos

**1.1.** Expliquem o que são uma partição, um sistema de ficheiros e um ponto de montagem, com exemplos do vosso esquema.

<br><br><br>

**1.2.** Para que servem a partição de sistema EFI e o carregador de arranque (GRUB)?

<br><br><br>

## 2. Planear o esquema de partições (antes de instalar)

| Partição | Tamanho | Sistema de ficheiros | Ponto de montagem | Justificação |
| --- | --- | --- | --- | --- |
| /dev/sda1 | | | | |
| /dev/sda2 | | | | |
| /dev/sda3 | | | | |

**2.1.** Justifiquem o esquema escolhido: tamanhos, sistemas de ficheiros e pontos de montagem.

<br><br><br>

**2.2.** Partição swap ou ficheiro de swap: qual a diferença e qual usa a vossa instalação?

<br><br><br>

## 3. Investigar o problema da equipa

**3.1.** Concordam com a afirmação do vosso cenário? Que dados do instalador apoiam ou contrariam a afirmação?

<br><br><br>

**3.2.** Que escolha do instalador teria consequências irreversíveis no vosso cenário? Porquê?

<br><br><br>

## 4. Instalar e registar evidências

Instalem o Ubuntu na bancada até iniciarem sessão no sistema instalado. Registem o que configuraram:

| Verificação | Valor definido / observado | Evidência (captura, relatório ou comando) |
| --- | --- | --- |
| Língua e teclado | | |
| Rede durante a instalação | | |
| Seleção de aplicações e software adicional | | |
| Tipo de instalação do disco | | |
| Partições criadas | | |
| Nome do computador e utilizador | | |
| Fuso horário | | |
| Primeiro arranque (do disco? sessão iniciada?) | | |

**4.1.** No separador Terminal Ubuntu, executem `lsblk`, `df -h`, `free -h` e `hostname`. O que confirma cada comando sobre a vossa instalação?

<br><br><br>

## 5. Parecer técnico e passagem ao Laboratório 04

**5.1.** Redijam uma conclusão técnica (6 a 8 linhas): instalação feita, escolhas principais, limitações, riscos e próximo passo seguro.

<br><br><br><br>

**Autoavaliação:** ☐ Colaborei ☐ Justifiquei as escolhas de particionamento ☐ Registei evidências ☐ Reconheci o que era irreversível

**Regra de segurança:** numa máquina real, nunca apagar nem formatar partições sem confirmar o disco de destino, sem cópia de segurança e sem autorização da professora.

**Entrega:** relatório copiado da bancada (separador Relatório) e esta ficha preenchida.
