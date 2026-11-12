# RMX3624 — investigação de desbloqueio e root

**Estado: pesquisa inicial; procedimento NÃO validado para o aparelho. Não executar comandos do rascunho.**

Projeto público de investigação para o Realme C33 RMX3624, build indicado como `RMX3624_13.C.46`. O material recebido foi interrompido a meio do documento de backup: não é um projeto operacional completo. Não foram testados desbloqueio, root, backup por readback ou recuperação no aparelho.

## Navegação

- [Mapa mental](MINDMAP.md)
- [Pendências e validação](PENDENCIAS.md)
- [Rascunho original recebido](RASCUNHO-ORIGINAL.txt) — **não validado; contém comandos e afirmações potencialmente perigosos**

## Ordem segura de trabalho

1. Confirmar modelo, build, kernel e esquema real de partições, sem modificar o aparelho.
2. Fazer backup independente de ficheiros pessoais e verificar que abre noutro dispositivo.
3. Obter firmware **exato**, confirmar integridade e identificar uma estratégia viável de recuperação. Readback de partições, se possível, é complementar; pode conter dados sensíveis.
4. Investigar compatibilidade com o mecanismo de desbloqueio específico e riscos; o desbloqueio pode apagar os dados e causar perda irreversível ou brick.
5. Só depois de validação independente, analisar o método apropriado de Magisk e restaurar. Não existem scripts de escrita neste repositório.

## Atenção às hipóteses

- Sem prova no aparelho, `MODULE_SIG_FORCE=y`, compatibilidade com KernelSU, Virtual A/B, nomes de partições e endereços FDL são **por confirmar**. O rascunho contém dois hashes de kernel diferentes: `g3bdf085cac44` e `g3bdfc085cac44`.
- A CVE-2022-38694 está descrita pelo projeto de referência como falha de BootROM e a sua aplicabilidade a este aparelho/build não foi demonstrada. Não se confirma aqui gravação de OTP nem reversibilidade.
- Não assumir que é preciso desativar AVB, gravar nos dois slots, ou que `fastboot boot` funciona. Qualquer relock com imagens não conformes pode deixar o telefone sem arrancar.
- Não publicar firmware privado, dumps, números de série, IMEI, credenciais ou logs pessoais.

## Fontes

- [CVE-2022-38694 — projeto de referência](https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader)
- [spreadtrum_flash — documentação](https://github.com/ilyakurdyukov/spreadtrum_flash)
- [Instalação oficial do Magisk](https://topjohnwu.github.io/Magisk/install.html)
- [Magisk no GitHub](https://github.com/topjohnwu/Magisk)

Este projeto não é afiliado à realme, Unisoc nem aos autores das ferramentas. Não inclui ficheiros de firmware.
