# Alinhamento com o programa de Sistemas Operativos

> O plano atualizado, com os dois trilhos (Windows e Ubuntu) e o estado de cada lab, está em [roteiro.md](roteiro.md). Este documento resume o que o referencial pede.

Este documento liga os laboratórios da bancada ao referencial do Curso Profissional de **Técnico/a de Desenvolvimento de Software** (nível 4, área 481), nas duas unidades do 10.º ano.

| Módulo | Código | Unidade de competência | Período (10.º TDS 2026/27) |
| --- | --- | --- | --- |
| 1 | UC02829 | Instalar, configurar e parametrizar sistemas operativos | 14/09/2026 – 18/03/2027 |
| 2 | UC01990 | Instalar, configurar e atualizar software complementar aos sistemas operativos | 06/04/2027 – 29/06/2027 |

## O que o referencial pede na UC02829

- **Realizações:** instalar sistemas operativos nos equipamentos informáticos e parametrizar os seus recursos.
- **Conhecimentos:**
  - requisitos e funcionalidades dos SO e características do equipamento;
  - instalação a partir de periféricos e respetivos parâmetros;
  - configuração de periféricos;
  - segurança da informação e ambiente de trabalho;
  - gestão de processos, memória, ficheiros e recursos;
  - privilégios de acesso.
- **Aptidões:**
  - interpretar manuais e tutoriais;
  - operar diferentes SO e definir as configurações de arranque;
  - usar o gestor de dispositivos e otimizar o rendimento;
  - definir como os dados são escritos, armazenados e recuperados;
  - gerir a partilha de recursos e ficheiros;
  - definir privilégios por perfil de utilizador.
- **Critérios de desempenho:** cumprir as orientações e os procedimentos técnicos em todas as fases, respeitando as recomendações técnicas e as necessidades do utilizador.

## Mapa dos laboratórios

| Lab | Tema | Conhecimentos e aptidões trabalhados | Na bancada |
| --- | --- | --- | --- |
| 01 | Interpretar o equipamento | Requisitos e funcionalidades dos SO; características do equipamento; interpretar documentação técnica; configurações de arranque (UEFI/Legacy, Secure Boot, TPM) | Firmware simulado; tabela de requisitos corrigida |
| 02 | Planear e criar a VM | Características do equipamento; gestão de memória e recursos; limitações do anfitrião | Hipervisor simulado com medidores |
| 03 | Instalar o Ubuntu | Instalação a partir de periféricos (ISO) e respetivos parâmetros; configurações de arranque (EFI, GRUB, ordem de arranque); escrita e armazenamento de dados (partições, sistemas de ficheiros, montagem); contas e segurança básica | Instalador simulado com particionamento manual |
| 04 | Instalar o Windows 11 *(planeado)* | Instalação e parâmetros; partições criadas pelo instalador; conta local vs Microsoft; requisitos TPM/Secure Boot na prática | Instalador Windows simulado |
| 05 | Pós-instalação *(planeado)* | Configuração de periféricos e gestor de dispositivos; rede; ambiente de trabalho | Terminais: `ipconfig`, `ip a`, `systeminfo`, `hostname` |
| 06 | Discos e sistemas de ficheiros *(planeado)* | Escrita, armazenamento e recuperação de dados; NTFS/FAT32/exFAT/ext4; GPT/MBR | Terminais: `lsblk`, `df -h`, `diskpart` |
| 07 | Utilizadores, permissões e partilha *(planeado)* | Privilégios por perfil; partilha de recursos e ficheiros | Terminais: `useradd`, `chmod`, `net user` |
| 08 | Processos, memória e arranque *(planeado)* | Gestão de processos e memória; otimizar o rendimento; serviços | Terminais: `ps`, `top`, `tasklist`, `free -h` |

## Módulo 2 · UC01990 (abril a junho)

O referencial pede:

- configurar ferramentas de sistema;
- criar imagens de restauro e cópias de segurança;
- fazer a manutenção, a atualização e o restauro do sistema;
- operar mecanismos de segurança (antivírus, firewall).

Labs previstos:

| Lab | Tema |
| --- | --- |
| 09 | Instalar e gerir software (winget, MSI, apt, snap) |
| 10 | Atualizações automáticas e manuais (Windows Update, `apt upgrade`) |
| 11 | Segurança: antivírus, firewall (`ufw`, Firewall do Windows) |
| 12 | Cópias de segurança, imagens de restauro e restauro do sistema |

## Avaliação

Cada lab produz evidências comparáveis:

- verificações automáticas (tabela, requisitos do cliente, missões);
- respostas escritas;
- registo de ações (firmware, VM, comandos);
- parecer técnico.

O relatório gerado pela bancada junta tudo para a entrega.
