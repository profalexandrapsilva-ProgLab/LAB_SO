# Roteiro dos trilhos de Sistemas Operativos

Um produto com dois trilhos separados, **Windows 11** e **Ubuntu 24.04**, cada um com uma máquina simulada própria. Cada lab tem cinco fases: **Aprender, Praticar, Avaria, Verificar e Comparar**. Há cenários para 8 equipas de 2 alunos, e as missões são verificadas pelo estado do sistema.

## Mapa dos labs

| Código | Trilho | Lab | Conteúdos-chave | Onde | Estado |
| --- | --- | --- | --- | --- | --- |
| C1 | Comum | Interpretar o equipamento | Requisitos W11/Ubuntu, UEFI, TPM, Secure Boot | Bancada · Lab 01 | Pronto |
| C2 | Comum | Planear e criar a VM | Anfitrião, hipervisor, recursos | Bancada · Lab 02 | Pronto |
| W1 | Windows | Instalar o Windows 11 | TPM, partições EFI/MSR/Recuperação, conta local | — | Por fazer |
| W2 | Windows | Definições e ambiente de trabalho | Definições, Painel de Controlo, energia, região | — | Por fazer |
| W3 | Windows | Dispositivos e controladores | Gestor de Dispositivos, códigos de erro, pnputil | — | Por fazer |
| W4 | Windows | Discos e sistemas de ficheiros | Gestão de Discos, diskpart, NTFS/exFAT, GPT/MBR | — | Por fazer |
| W5 | Windows | Contas, UAC e permissões NTFS | Contas locais, grupos, UAC, herança, icacls | Trilhos · W5 | Pronto |
| W6 | Windows | Partilha de pastas | SMB, partilha vs NTFS, net share | — | Por fazer |
| W7 | Windows | Processos, serviços e arranque | Gestor de Tarefas, services.msc, arranque | — | Por fazer |
| W8 | Windows | Rede e diagnóstico | ipconfig, netsh, ping, nslookup, tracert | — | Por fazer |
| L1 | Ubuntu | Instalar o Ubuntu | Partições, EFI, GRUB, conta, fuso | Bancada · Lab 03 | Pronto |
| L2 | Ubuntu | Terminal e árvore de diretórios | FHS, caminhos, nano, man | — | Por fazer |
| L3 | Ubuntu | Dispositivos e controladores | lspci, lsusb, lsmod, dmesg | — | Por fazer |
| L4 | Ubuntu | Discos e sistemas de ficheiros | lsblk, fdisk, mkfs, mount, /etc/fstab | — | Por fazer |
| L5 | Ubuntu | Utilizadores, grupos e permissões | useradd, groupadd, sudo, chmod, chown, setfacl | Trilhos · L5 | Pronto |
| L6 | Ubuntu | Partilha com Samba | smb.conf, testparm, smbpasswd | — | Por fazer |
| L7 | Ubuntu | Processos, serviços e arranque | ps, top, kill, systemctl, journalctl | — | Por fazer |
| L8 | Ubuntu | Rede e diagnóstico | ip, nmcli, ss, resolvectl, traceroute | — | Por fazer |
| W9–W12 | Windows (M2) | Software, atualizações, segurança, cópias | winget, Windows Update, Defender, Firewall, wbadmin | — | Por fazer |
| L9–L12 | Ubuntu (M2) | Software, atualizações, segurança, cópias | apt, snap, unattended-upgrades, ufw, rsync, cron | — | Por fazer |
| P1 | Ponte | A mesma tarefa nos dois sistemas | Comparar e justificar a escolha do SO | — | Por fazer |

## Ordem de construção

1. W5 + L5, utilizadores e permissões (pronto; falta testar com alunos).
2. W1, instalar o Windows 11.
3. W4 + L4, discos e sistemas de ficheiros.
4. W2 + L2, ambiente de trabalho e terminal.
5. W3 + L3, dispositivos e controladores.
6. W7 + L7, processos, serviços e arranque.
7. W8 + L8 (rede) e W6 + L6 (partilhas).
8. Módulo 2 (W9 a W12 e L9 a L12), até abril de 2027.
9. P1 (lab ponte) e painel do professor.

## Em aberto

- [ ] Licença e nome final do produto.
- [ ] Painel do professor com dados partilhados (exige alojamento com base de dados).
- [ ] Peso de cada fase na nota.
- [ ] Guia do professor num repositório privado.
