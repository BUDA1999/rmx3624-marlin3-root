# Guia de investigação — RMX3624

# Perfil do dispositivo — a confirmar

## Identificação declarada no rascunho

- Modelo: RMX3624 (Realme C33)
- Build: `RMX3624_13.C.46`; incremental indicado `O_V1_P16`
- Plataforma indicada: `sc2355_marlin3_lite` / UMS9230 (T612)
- Kernel declarado: `5.4.254-android12-9`
- Android declarado: 13

## Divergência importante

O rascunho contém dois hashes de kernel diferentes: `g3bdf085cac44` e `g3bdfc085cac44`. Portanto, o perfil não está fechado. Confirmar a partir do próprio dispositivo e de firmware oficial correspondente, sem publicar identificadores pessoais.

A existência de A/B, Virtual A/B, partições `boot_a`/`boot_b` ou o estado `MODULE_SIG_FORCE` também não está comprovada. Não inferir a configuração deste modelo a partir do Realme C53 ou de outro dispositivo com kernel semelhante.

## Risco

Desbloqueio/root podem causar wipe, falha de arranque, perda de garantia/serviços e exposição de dados. Confirmar antes se há recuperação oficial funcional para a variante exata.


---

# Pré-requisitos — pesquisa segura

Antes de qualquer alteração, identificar o modelo/build exatos, consultar documentação oficial e guardar dados pessoais num local separado. Confirmar que o backup pode ser aberto noutro dispositivo.

Para trabalho técnico, usar um computador confiável, cabo de dados e bateria suficiente. Obter firmware apenas de fonte legítima para a variante e região exatas; verificar o checksum publicado pelo fornecedor, quando disponível. Não descarregar nem partilhar PAC, dumps ou imagens de firmware neste repositório.

A documentação do `spreadtrum_flash` declara suporte testado limitado e alerta para diferenças entre aparelhos. Isso não valida o RMX3624. O uso de FDL de outro aparelho pode acarretar risco; não experimentar endereços de memória “vizinhos”.

Não continuar sem um método de recuperação específico e comprovado para a build. Não usar test point improvisado nem ferramentas de gravação destrutivas com base apenas neste guia.


---

# Backup obrigatório — plano, não procedimento de readback

**Não alterar o bootloader nem partições antes de concluir e testar o backup dos dados pessoais.** Copiar fotos, documentos, contactos e ficheiros importantes para armazenamento independente e confirmar que se conseguem abrir. Guardar também os meios de recuperar as contas e apps essenciais.

Um dump de partições não equivale a backup utilizável dos dados pessoais; pode conter material cifrado, identificadores e dados de rádio altamente sensíveis. Não carregar dumps para GitHub, serviços públicos ou conversas.

Antes de qualquer alteração de firmware, exigir documentação específica que confirme: método compatível de leitura/restauro, identidade exata de cada partição, integridade dos ficheiros, e possibilidade real de recuperar o aparelho. O texto original propunha comandos e endereços não verificados; foram omitidos e não devem ser executados.

Checklist:
- [ ] Backup pessoal copiado para dois locais independentes
- [ ] Restauro dos ficheiros testado
- [ ] Identidade e build confirmadas
- [ ] Firmware oficial correspondente localizado e checksum conferido
- [ ] Plano de recuperação comprovado para a variante exata
- [ ] Riscos de wipe, brick e irreversibilidade aceites


---

# Desbloqueio do bootloader — riscos e validação

O rascunho propõe a CVE-2022-38694, mas não demonstra que o RMX3624 na build `13.C.46` seja vulnerável nem que os binários/endereço propostos se apliquem à variante `marlin3_lite`. A existência de uma CVE para uma família de chips não prova vulnerabilidade de uma build específica.

Não executar o exploit, gravar `uboot`, alterar OTP ou seguir comandos de desbloqueio de outro modelo com base neste repositório. Uma falha pode inutilizar o telefone; alegações de que um travamento é inofensivo não foram verificadas.

Preferir o procedimento oficial do fabricante, quando disponível. Se não houver caminho oficial, procurar pesquisa independente específica para RMX3624/build, verificar hashes e compatibilidade das fontes e obter um plano de recuperação antes de considerar qualquer experimento. Não relockar após uma alteração não-stock sem documentação confiável específica.


---

# Root com Magisk — visão geral, não instruções específicas para RMX3624

A instalação do Magisk depende da partição correta e do estado do bootloader. A documentação oficial indica que, conforme o dispositivo, a imagem a patchar pode ser `boot`, `init_boot`, `vendor_boot` ou `recovery`; isso precisa ser confirmado para o modelo/build exatos.

Não está verificado que o RMX3624 aceite `fastboot boot`, que precise desativar AVB, ou que seja seguro/gratuito gravar a mesma imagem nos dois slots. Não executar os comandos do rascunho. Não usar imagem patchada de outra pessoa ou dispositivo.

Consultar [instalação oficial do Magisk](https://topjohnwu.github.io/Magisk/install.html) e [avisos oficiais](https://github.com/topjohnwu/Magisk). Só prosseguir quando houver método específico, firmware e recuperação comprovados. O estado root deste aparelho permanece **não testado**.


---

# Verificação pós-alteração

Não há root instalado nem verificações executadas neste aparelho. Para uma eventual instalação autorizada e validada, registar apenas informações não sensíveis que ajudem a confirmar boot, estado do bootloader e funcionamento básico; não publicar identificadores, logs completos ou dados de apps.

Não tentar ocultar root nem contornar Play Integrity, mecanismos anti-fraude ou verificações de apps bancárias/CRM. A disponibilidade e compatibilidade dos serviços pode mudar e não é garantida pelo projeto.


---

# Restauro e relock — aviso crítico

Este projeto não fornece comandos de restauro/relock: não há imagem verificada nem procedimento confirmado para o RMX3624/build indicados. Relock com partições incompatíveis ou modificadas pode impedir o arranque e exigir recuperação de serviço.

Não zerar marcadores em `misc`/`miscdata`, não escrever offsets e não restaurar `vbmeta` ou boot a partir de dumps de origem incerta. Não assumir que um backup isolado seja suficiente para rollback. Usar apenas procedimento oficial comprovado para modelo, região e versão exatos; na dúvida, procurar assistência qualificada antes de qualquer escrita.


---

# Troubleshooting — sem comandos destrutivos

| Situação | Conduta segura |
|---|---|
| Ferramenta não detecta o aparelho | Parar; confirmar cabo, porta, drivers e documentação oficial. Não improvisar test point. |
| Handshake/FDL falha | Não experimentar endereços aleatórios nem FDL de outra variante. Recolher apenas mensagem não sensível e rever compatibilidade. |
| Bootloader continua bloqueado | Não repetir gravações de exploit. Confirmar se existe método oficial e específico. |
| Bootloop após alteração | Não continuar a flashar imagens adivinhadas; usar recuperação oficial para a build exata ou assistência qualificada. |
| Aparelho não inicia nem entra em modo de recuperação | Não seguir pinagem de placa genérica; procurar reparação qualificada. |
| App sensível deixa de funcionar | Contactar o fornecedor; não contornar verificações de integridade/segurança. |


---

# Mapa de partições — conceitos, não inventário confirmado

| Nome comum | Função geral (varia por dispositivo) | Estado neste projeto |
|---|---|---|
| `boot`, `init_boot`, `vendor_boot`, `recovery` | componentes de arranque/ramdisk | partição correta não confirmada |
| `vbmeta` | metadados de verificação de arranque | nomes/slots e configuração não confirmados |
| `uboot`, `splloader` | etapas iniciais de arranque em algumas plataformas | nomes e método de acesso não confirmados |
| `dtbo` | overlays de device tree | nomes/slots não confirmados |
| `super` | partições dinâmicas em alguns aparelhos | presença e layout não confirmados |
| `persist`, `prodnv`, `nvdata`, `nvram`, `modem` | áreas que podem conter calibração/rádio/identificadores | altamente sensíveis; não compartilhar nem alterar |
| `misc` | metadados de boot em algumas implementações | não usar para relock manual |

A lista original é uma hipótese, não uma tabela lida do telefone. Nomes, slots, tamanhos e funções devem ser verificados por documentação específica. Nunca publicar dumps ou hashes de dados de partições sensíveis.


---

# LOG de investigação

Formato: `data | etapa | evidência não sensível | resultado`

## 2026-11-12
- Repositório criado para organizar pesquisa e mapa mental.
- Nenhum procedimento testado no RMX3624.
- O rascunho é mantido como registo não validado; o guia separa as hipóteses dos passos seguros.
