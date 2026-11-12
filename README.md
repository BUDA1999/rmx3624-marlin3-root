# RMX3624 — investigação de desbloqueio e root

Projeto de pesquisa para o Realme C33 RMX3624 e build indicada `RMX3624_13.C.46`.

> **Estado: não validado no aparelho. Não há procedimentos executáveis neste repositório.** Desbloquear o bootloader pode apagar os dados; escrita errada pode inutilizar o dispositivo. O rascunho original é preservado apenas como registo: contém comandos perigosos e não validados, **não os executes**.

## Mind map

Veja o [mapa mental](MINDMAP.md), renderizado pelo GitHub.

## Documentação

- [Guia de investigação e capítulos de segurança](GUIA-DE-INVESTIGACAO.md)
- [Pendências de validação](PENDENCIAS.md)
- [Rascunho original — parte 1](RASCUNHO-ORIGINAL.txt) e [continuação](RASCUNHO-CONTINUACAO.txt): não validados, não executar

## Importante

Os detalhes fornecidos para este aparelho ainda não foram demonstrados com evidências reproduzíveis. O texto original contém hashes divergentes do kernel e endereços/nomes presumidos. Não assumir que a CVE se aplica à build, que existe Virtual A/B, que `fastboot boot` funciona, ou que sejam necessários AVB alterado e escrita em ambos os slots.

Nunca publique firmware, dumps, IMEI, números de série, chaves, dados pessoais ou credenciais. Este repositório não inclui firmware nem dumps.

## Referências

- [Projeto de referência CVE-2022-38694](https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader)
- [spreadtrum_flash](https://github.com/ilyakurdyukov/spreadtrum_flash)
- [Instalação oficial do Magisk](https://topjohnwu.github.io/Magisk/install.html)
- [Magisk no GitHub](https://github.com/topjohnwu/Magisk)

Não afiliado à realme, Unisoc ou aos autores das ferramentas.
