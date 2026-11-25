# Laboratório 01: Interpretar o equipamento

**10.º TDS · Sistemas Operativos · UC02829** · trabalho a pares · 90 + 45 min · Bancada de SO → **Lab 01 · Equipamento**

## Objetivo

Perante o pedido de um cliente, interpretar o hardware de um PC, confirmar no firmware os dados em falta e avaliar a compatibilidade com o **Windows 11** e o **Ubuntu Desktop**. No fim, a equipa recomenda o sistema mais adequado.

## Cenários das equipas

| Equipa | PC | Pedido do cliente | Equipamento (dados fornecidos) | Desafio técnico |
| --- | --- | --- | --- | --- |
| 01 | PC-A · Escritório antigo | Associação: correio eletrónico, documentos e navegação. Quer manter o equipamento. | Core i5-6500 · 8 GB · HDD 500 GB · TPM não identificado · arranque desconhecido | A substituição do HDD por SSD resolve necessariamente todos os problemas de desempenho? |
| 02 | PC-B · Portátil empresarial | Pequena empresa: documentos, videochamadas, serviços online. Evitar interrupções. | Core i5-8250U · 8 GB · SSD 256 GB · UEFI · TPM e Secure Boot desconhecidos | Porque é importante distinguir UEFI, TPM e Secure Boot na preparação da instalação? |
| 03 | PC-C · Posto de desenvolvimento | Aluno de programação: desenvolver e experimentar software em segurança. | Ryzen 5 5600G · 16 GB · SSD 512 GB · UEFI · TPM por verificar | Porque não devemos atribuir todos os recursos do computador a uma máquina virtual? |
| 04 | PC-D · Computador limitado | Biblioteca: páginas web e documentos simples, orçamento muito reduzido. | Celeron N4020 · 4 GB · eMMC 64 GB · firmware e TPM por verificar | Cumprir os requisitos mínimos garante uma utilização rápida e confortável? |
| 05 | PC-E · Computador sem SO | Oficina: preparar um PC sem SO para trabalho administrativo. | Core i3-10100 · 8 GB · SSD 240 GB · arranque e TPM desconhecidos | Que verificações de firmware e arranque devem ser feitas antes de instalar? |
| 06 | PC-F · Estação de trabalho antiga | Empresa: reutilizar para armazenamento local e tarefas básicas. | Core i7-4770 · 16 GB · HDD 1 TB · arranque Legacy · TPM desconhecido | Como se relacionam o modo de arranque e o esquema de partições? |
| 07 | PC-G · Equipamento recente | Equipa: produtividade, videoconferências e programação. | Ryzen 5 7530U · 16 GB · SSD 512 GB · UEFI · Secure Boot/TPM por verificar | Como influenciam RAM e CPU a execução simultânea de várias aplicações? |
| 08 | PC-H · Configuração incompleta | O PC funcionava, mas a nova instalação levantou dúvidas de compatibilidade. | Core i5-8400 · 8 GB · SSD 128 GB · UEFI · Secure Boot desativado · TPM desconhecido | Secure Boot desativado significa, por si só, incompatibilidade definitiva? |

## Missões

1. **Interpretar o equipamento.** Ligar o PC simulado, entrar no firmware (F2 ou DEL) e abrir os separadores Principal, Avançado, Arranque e Segurança. Só alterar valores com autorização (caixa na bancada).
2. **Pesquisar os requisitos oficiais** e preencher a tabela Cumpre / Não cumpre / Por confirmar. A bancada corrige a tabela. «Por confirmar» só é aceite enquanto o dado não tiver sido verificado no firmware.
3. **Resolver o pedido:** comparar os dois sistemas e indicar dois cuidados antes de instalar.
4. **Preparar a próxima intervenção:** três verificações, por ordem, antes de instalar.
5. **Parecer técnico** de 6 a 8 linhas.

Fontes oficiais: [requisitos do Windows 11](https://learn.microsoft.com/windows/whats-new/windows-11-requirements) · [requisitos do Ubuntu](https://help.ubuntu.com/community/Installation/SystemRequirements)
