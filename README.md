# SO Lab · Laboratórios de Sistemas Operativos

Laboratórios práticos de **Sistemas Operativos** que correm no navegador, sem máquinas virtuais. São para trabalho **a pares (2 alunos)** e seguem a UC02829 (*Instalar, configurar e parametrizar sistemas operativos*) e a UC01990 (*Instalar, configurar e atualizar software complementar aos sistemas operativos*).

![SO Lab · Trilhos](docs/img/trilhos.png)

## As três partes

| Página | Endereço | O que é |
| --- | --- | --- |
| **Trilhos** | `/` | Produto principal. Dois trilhos, **Windows 11** e **Ubuntu 24.04**, cada um com a sua máquina simulada. Cada lab tem cinco fases: Aprender, Praticar, Avaria, Verificar e Comparar. Já disponíveis: **W5** (contas, UAC e permissões NTFS) e **L5** (utilizadores, grupos e permissões). |
| **Bancada** | `/bancada/` | Labs comuns e de instalação: **Lab 01** (interpretar o equipamento, com firmware UEFI simulado), **Lab 02** (planear e criar a VM, com hipervisor simulado) e **Lab 03** (instalar o Ubuntu, com instalador simulado). Tem cenários para as 8 equipas. |
| **Revisão** | `/revisao/` | 16 labs curtos de revisão de conceitos, com consola de comandos reais, perguntas baralhadas e resposta escrita verificada. |

Todas as páginas pedem os nomes e números do **Aluno A** e do **Aluno B** e geram um relatório da equipa para entregar.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub (por exemplo `so-lab`).
2. Carregue **todo o conteúdo desta pasta**, mantendo as subpastas `bancada/`, `revisao/`, `docs/` e `fichas/` e o ficheiro `.nojekyll`. No site do GitHub: **Add file → Upload files** e arraste os ficheiros e as pastas.
3. Abra **Settings → Pages**. Em **Build and deployment**, escolha **Deploy from a branch**, depois a branch `main` e a pasta `/ (root)`. Clique em **Save**.
4. Ao fim de um ou dois minutos, o site fica em `https://<utilizador>.github.io/so-lab/`.

Endereços diretos, úteis para o Classroom ou o Moodle:

- Trilhos: `…/#w5`, `…/#l5`, `…/#relatorio`
- Bancada: `…/bancada/#lab01`, `#lab02`, `#lab03`, `#linux`, `#windows`, `#relatorio`
- Revisão: `…/revisao/`

Para a pré-visualização do repositório nas redes sociais, use `docs/img/capa.png` em **Settings → General → Social preview**.

## Como os alunos trabalham

1. Abrem a página, escrevem os nomes e números dos dois alunos e escolhem a equipa (01 a 08). A equipa define o cenário: empresa, utilizadores, grupos e pastas.
2. Fazem o lab. As missões são verificadas automaticamente pelo **estado** da máquina simulada, por isso qualquer caminho correto conta.
3. No **Relatório**, carregam em **Copiar relatório** ou **Descarregar** e entregam o texto.

> O progresso fica no navegador do PC onde a equipa trabalha (`localStorage`). Se a equipa mudar de PC ou limpar o navegador, recomeça. Nenhum dado é enviado para servidores.

## Estrutura

```
index.html              Trilhos (página principal)
bancada/index.html      Bancada: Labs 01, 02 e 03 e terminais de prática
revisao/index.html      Revisão: 16 labs de conceitos
fichas/                 Fichas imprimíveis dos Labs 01 a 03
docs/roteiro.md         Plano de todos os labs dos trilhos e estado de cada um
docs/programa.md        Alinhamento com a UC02829 e a UC01990
docs/img/               Capturas e imagem de capa
.nojekyll               Impede o GitHub de processar as páginas
```

## Avisos

- **Soluções:** o guia do professor, com respostas e grelhas, fica fora deste repositório público.
- **Simulação:** os comandos e as janelas são reais, mas as saídas são simuladas. Cada página diz isso aos alunos.
- **Requisitos oficiais:** a correção do Lab 01 segue as páginas da [Microsoft](https://learn.microsoft.com/windows/whats-new/windows-11-requirements) e do [Ubuntu](https://help.ubuntu.com/community/Installation/SystemRequirements). Reveja-as no início de cada ano letivo.
- **Licença:** escolha uma antes de tornar o repositório público (por exemplo, CC BY-SA 4.0) e acrescente o ficheiro `LICENSE`.

Autoria: Alexandra Silva @ 2026
