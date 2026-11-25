# Laboratório 02: Planear e criar a máquina virtual

**10.º TDS · Sistemas Operativos · UC02829** · trabalho a pares · 90 + 45 min · Bancada de SO → **Lab 02 · Máquina virtual**

## Objetivo

Distinguir anfitrião, máquina virtual e hipervisor. Propor e criar uma VM Ubuntu 24.04 adequada aos recursos do anfitrião, sem iniciar a instalação, e investigar o problema específico da equipa.

## Cenários das equipas (dados simulados)

| Equipa | Anfitrião | Pedido do cliente | RAM · CPU · SSD livre | Problema para investigar |
| --- | --- | --- | --- | --- |
| 01 | LAB-A · Pouca memória | Testar Ubuntu sem bloquear o PC do aluno. | 8 GB · 4 núcleos · 110 GB | «O técnico sugere atribuir 6 GB à VM e deixar apenas 2 GB ao anfitrião.» |
| 02 | LAB-B · Espaço insuficiente | VM Ubuntu agora e estudar uma futura VM Windows 11. | 16 GB · 6 núcleos · 72 GB | «Foi proposta uma VM Windows 11 com disco virtual de 40 GB como solução definitiva.» |
| 03 | LAB-C · Hipervisor por confirmar | PC com capacidade aparente, sem confirmar se executa VMs. | 16 GB · 4 núcleos · 190 GB · virtualização por verificar | «Um colega afirma que 16 GB RAM garantem que qualquer hipervisor funciona.» |
| 04 | LAB-D · Dois sistemas, um PC | Testar Windows e Ubuntu sem alterar a instalação principal. | 24 GB · 8 núcleos · 260 GB | «O cliente pergunta se é obrigatório manter as duas VMs ligadas ao mesmo tempo.» |
| 05 | LAB-E · Equipamento limitado | Um PC antigo tem de participar na aula prática. | 4 GB · 2 núcleos · 55 GB | «O cliente exige executar uma VM Windows 11 com ambiente gráfico completo.» |
| 06 | LAB-F · Disco dinâmico | Criar a VM e preservar espaço no SSD físico. | 16 GB · 4 núcleos · 95 GB | «Um colega confunde o tamanho máximo do disco virtual dinâmico com espaço logo ocupado.» |
| 07 | LAB-G · Rede e isolamento | Testar comandos de rede sem expor serviços à rede da escola. | 16 GB · 6 núcleos · 180 GB | «Um aluno propõe usar modo Bridge sem avaliar as consequências.» |
| 08 | LAB-H · Arranque e imagem ISO | A VM mostra «No bootable medium found». | 16 GB · 4 núcleos · 150 GB | «O responsável afirma que basta aumentar a RAM para corrigir a mensagem.» |

## Missões

1. **Rever os conceitos:** anfitrião, VM e hipervisor; recursos partilhados e limitações do anfitrião.
2. **Preparar a proposta técnica:** CPU, RAM, disco (tamanho e tipo), firmware e ISO. Os medidores da bancada mostram a RAM, os núcleos e o SSD consumidos.
3. **Investigar o problema da equipa:** testar a afirmação no simulador e comparar com a proposta da equipa.
4. **Criar a VM e arrancá-la sem instalar.** A tabela de evidências é preenchida a partir da configuração da VM.
5. **Conclusão técnica** e passagem ao Laboratório 03.

**Regra de segurança:** não alterar o sistema anfitrião nem iniciar instalações sem autorização da professora.
