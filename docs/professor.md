# Guia do professor

Respostas esperadas, pistas por equipa e grelhas. Este ficheiro destina-se ao professor: se o repositório for público, considere movê-lo para um repositório privado.

## Lab 01 · Resultado esperado da tabela (depois de verificar o firmware)

C = Cumpre · NC = Não cumpre · PC = Por confirmar

| PC | W11 CPU | W11 RAM | W11 disco | W11 firmware | W11 TPM | Ubuntu | O que o firmware revela |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A · i5-6500 | **NC** (fora da lista de CPUs aprovadas) | C | C | C (UEFI capaz, mas em Legacy/CSM com disco MBR) | C (Intel PTT 2.0 desativado) | C em tudo | Mudar para UEFI sem converter o disco (mbr2gpt) faz o PC deixar de arrancar |
| B · i5-8250U | C | C | C | C | C | CPU C ou PC (base 1,6 GHz, turbo 3,4) | UEFI, Secure Boot ativo, PTT 2.0 ativo |
| C · Ryzen 5 5600G | C | C | C | C | C (fTPM 2.0 desativado → ativar) | C | Ativar o fTPM não apaga dados |
| D · Celeron N4020 | C | C (no limite) | C (64 GB, no limite) | C | C | CPU NC ou PC (1,1 GHz) | Cumpre o mínimo, mas fica lento: tema do desafio |
| E · i3-10100 | C | C | C | C (Secure Boot desativado, mas capaz) | C | C | Disco vazio: «Reboot and select proper boot device» |
| F · i7-4770 | **NC** | C | C | C (UEFI capaz, Legacy ativo, MBR) | **NC** (sem TPM) | C | Windows 11 inviável; Ubuntu é a escolha adequada |
| G · Ryzen 5 7530U | C | C | C | C | C | C | Tudo ativo |
| H · i5-8400 | C | C | C | C (Secure Boot desativado, mas capaz) | C | C | Basta ativar o Secure Boot (requisito: *Secure Boot capable*) |

**Pistas para a recomendação:**

- **A e F:** Ubuntu, porque o CPU não é suportado pelo Windows 11.
- **D:** Ubuntu ou um sabor mais leve. Com 4 GB e eMMC lenta, cumprir o mínimo não garante conforto.
- **B, C, E, G e H:** ambos são viáveis. A escolha depende do software do cliente (por exemplo, compatibilidade empresarial no B e ambiente de desenvolvimento no C).

## Lab 02 · Pistas por equipa

| Equipa | Resposta esperada ao problema |
| --- | --- |
| 01 · LAB-A (8 GB) | Discordar: com 6 GB na VM, o anfitrião fica com 2 GB e bloqueia. Propor 3 a 4 GB. A bancada avisa quando ficam menos de 4 GB para o anfitrião. |
| 02 · LAB-B (72 GB livres) | Discordar: o Windows 11 exige 64 GB de disco. Com 72 GB livres não cabem uma VM Windows 11 e uma Ubuntu em discos fixos. |
| 03 · LAB-C | Discordar: sem VT-x/AMD-V ativo no firmware a VM não arranca, por mais RAM que haja. A bancada mostra o erro até ativarem a virtualização. |
| 04 · LAB-D (24 GB) | Não é obrigatório. Executar em alternância poupa recursos. Em simultâneo cabe (por exemplo, 8 + 4 GB mais o anfitrião), mas com menos folga. |
| 05 · LAB-E (4 GB) | Discordar: o Windows 11 exige 4 GB só para a VM e o anfitrião ficaria sem memória. Alternativa: Ubuntu com 2 GB (lento) ou um sabor leve. |
| 06 · LAB-F | Disco dinâmico: o tamanho é o máximo; no SSD só ocupa o que a VM escreve. Arrancar a VM mostra cerca de 2 GB ocupados. |
| 07 · LAB-G | Bridge põe a VM na rede da escola com IP próprio, visível para os outros PCs. Usar NAT ou rede interna. |
| 08 · LAB-H | Discordar: a mensagem significa que não há ISO montada e o disco está vazio. A RAM não resolve. |

## Lab 03 · Instalação esperada por equipa

**Comum a todas as equipas:**

- Português nas duas primeiras escolhas (língua e teclado);
- Lisboa no fuso horário;
- computador `ubu-eqNN`;
- utilizador em minúsculas;
- palavra-passe com 8 ou mais caracteres;
- ISO removida no ecrã «Please remove the installation medium»;
- sessão iniciada.

| Equipa | Caminho correto | Erro típico que a bancada mostra |
| --- | --- | --- |
| 01 | «Apagar o disco» ou manual sem swap. Depois, `free -h` mostra 2 GB de swap: é o `/swap.img`. | Pensar que é obrigatório criar uma partição swap |
| 02 | / com 20 GB ou mais (automático: EFI 1 GB + / 24 GB) | / com 6 GB → erro; com menos de 20 GB → aviso |
| 03 | Manual: EFI FAT32 1 GB em /boot/efi + / ext4 | Sem EFI em UEFI → erro «o GRUB não é instalado» |
| 04 | «Ao lado do Windows Boot Manager» (ou manual: reutilizar a EFI sem formatar + / no espaço livre). O GRUB mostra Ubuntu e Windows. | «Apagar o disco», ou remover/formatar partições existentes → Windows apagado, requisito falha |
| 05 | Seleção predefinida. Em BIOS, «Apagar o disco» cria só / (sem EFI). | Seleção alargada numa VM de 2 GB e 25 GB |
| 06 | Manual: EFI 1 GB + / 25 GB + /home com o resto. O disco é dinâmico: o SSD físico só cresce com o uso. | Achar que /home ocupa já o espaço no anfitrião |
| 07 | «Não ligar à Internet» (ou com fios: a rede interna não tem Internet), sem software de terceiros nem codecs | Marcar software adicional sem Internet → erro; podem instalar-se depois |
| 08 | Remover a ISO antes do ENTER | Premir ENTER sem remover → a VM volta a arrancar o instalador (a unidade ótica vem antes do disco na ordem de arranque) |

**Respostas de referência:**

- **1.1.** Uma partição é uma divisão lógica do disco. O sistema de ficheiros (ext4, FAT32, NTFS) é a forma como os dados são organizados nela. O ponto de montagem é a pasta onde a partição aparece na árvore (/, /home, /boot/efi).
- **1.2.** A partição EFI (FAT32) guarda os carregadores de arranque que o firmware UEFI executa. O GRUB é o carregador do Ubuntu: carrega o núcleo Linux e mostra o menu quando há vários sistemas.
- **2.2.** Uma partição swap é uma área fixa do disco. O ficheiro de swap (`/swap.img`, criado por omissão no Ubuntu) é mais flexível porque pode ser redimensionado. Ambos servem de memória de recurso quando a RAM acaba.

### Grelha sugerida (20 valores)

| Critério | Cotação |
| --- | --- |
| Requisitos comuns cumpridos (verificação da bancada, 5 requisitos) | 5 |
| Requisito específico da equipa cumprido | 3 |
| Esquema de partições planeado e justificado (2 e 2.1) | 3 |
| Conceitos (1.1, 1.2, 2.2) | 3 |
| Problema da equipa e consequências irreversíveis (3.1, 3.2) | 3 |
| Evidências e comandos (4, 4.1) | 1 |
| Parecer técnico (5.1) | 2 |
| **Total** | **20** |

## Trilhos · W5 (Windows) e L5 (Ubuntu): exemplo da equipa 01

Cenário: Clínica Sorriso. ana (responsável) e bruno estão no grupo rececao; carla está no grupo medicos. As pastas são Marcacoes e Fichas. As outras equipas seguem o mesmo esquema com os seus nomes.

### W5 · Uma solução no PowerShell

```powershell
New-LocalUser -Name ana -FullName "Ana Reis"        # repetir para bruno e carla
New-LocalGroup -Name rececao ; New-LocalGroup -Name medicos
Add-LocalGroupMember -Group rececao -Member ana,bruno
Add-LocalGroupMember -Group medicos -Member carla
net localgroup Administradores ana /add
icacls C:\Empresa\Marcacoes /inheritance:d
icacls C:\Empresa\Marcacoes /remove Utilizadores
icacls C:\Empresa\Marcacoes /grant rececao:(OI)(CI)M
icacls C:\Empresa\Fichas /inheritance:d
icacls C:\Empresa\Fichas /remove Utilizadores
icacls C:\Empresa\Fichas /grant medicos:(OI)(CI)M
icacls C:\Empresa\Fichas /grant rececao:RX
```

Para os testes: mudar de utilizador para bruno e criar um documento em Marcacoes; depois mudar para carla e tentar abrir Marcacoes (acesso negado). A missão do UAC: com a sessão de bruno ou carla, abrir a Gestão de Computadores.

**Avaria W5:** bruno tem «Negar: Escrita» explícito em Marcacoes. Solução: `icacls C:\Empresa\Marcacoes /remove:d bruno`, ou desmarcar o Negar em Propriedades → Segurança → Editar. **Erro a evitar:** dar Controlo total a Todos. A verificação deteta-o, porque a carla passaria a ter acesso.

### L5 · Uma solução

```bash
sudo groupadd rececao ; sudo groupadd medicos
sudo useradd -m ana ; sudo passwd ana          # repetir para bruno e carla
sudo usermod -aG rececao,sudo ana
sudo usermod -aG rececao bruno ; sudo usermod -aG medicos carla
sudo chgrp rececao /srv/empresa/Marcacoes ; sudo chmod 2770 /srv/empresa/Marcacoes
sudo chgrp medicos /srv/empresa/Fichas ; sudo chmod 775 /srv/empresa/Fichas
# desafio: sudo chmod 770 /srv/empresa/Fichas ; sudo setfacl -m g:rececao:rx /srv/empresa/Fichas
```

Para os testes: `su - bruno` e `touch /srv/empresa/Marcacoes/teste.txt` (funciona); `su - carla` e `cd /srv/empresa/Marcacoes` (Permissão recusada); `sudo whoami` como carla (recusado) e como ana (root).

**Avaria L5:** Marcacoes está em 2760. O grupo tem rw mas não tem x, por isso ninguém do grupo consegue entrar. Solução: `sudo chmod g+x /srv/empresa/Marcacoes`.

### Grelha sugerida por lab dos trilhos (20 valores)

| Fase | Critério | Cotação |
| --- | --- | --- |
| Praticar | Missões obrigatórias verificadas | 8 |
| Avaria | Resolvida sem dar acesso a mais + diagnóstico | 5 |
| Verificar | 6 perguntas (descontar 0,5 por tentativa errada registada) | 3 |
| Comparar | Reflexão justificada com exemplos do lab | 3 |
| Desafio | Missão de desafio (bónus até ao máximo de 20) | 1 |
