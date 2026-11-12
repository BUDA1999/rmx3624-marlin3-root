# Pendências e validação

## Antes de qualquer tentativa

- [ ] Registar evidências da identidade exata, versão e hash do kernel (os dois valores do rascunho divergem).
- [ ] Confirmar A/B ou Virtual A/B e inventário real das partições; nomes não são garantia de existência.
- [ ] Identificar build e configuração de assinatura de módulos do kernel real. Um kernel de outro modelo não prova a configuração deste.
- [ ] Verificar se existe firmware exato e íntegro e processo de recuperação específico e viável; não há garantia de que o readback seja acessível com bootloader bloqueado.
- [ ] Fazer backup dos dados pessoais e testar acesso em outro dispositivo. Um dump de partições não substitui backup utilizável de ficheiros cifrados.
- [ ] Investigar compatibilidade da CVE e endereços com fontes primárias para este hardware e build, sem assumir sucesso.
- [ ] Confirmar partição de ramdisk; a documentação Magisk admite boot, init_boot, vendor_boot ou recovery conforme o dispositivo.
- [ ] Avaliar AVB, suporte a test-boot e recuperação sem assumir que funcionam, nem que desativação de verificação é obrigatória.
- [ ] Não executar relock até existir orientação verificada para firmware e estado do aparelho.

## Limites do material fornecido

O texto recebido termina em `exec_addr 0x65015` e não inclui as restantes páginas ou scripts prometidos. O rascunho original é mantido apenas como registo, não como instrução. As afirmações sobre OTP, `MODULE_SIG_FORCE`, VAB, escrita em ambos os slots e obrigatoriedade de desativar AVB precisam de provas específicas antes de aceitação.

Fontes: [Magisk](https://topjohnwu.github.io/Magisk/install.html), [spreadtrum_flash](https://github.com/ilyakurdyukov/spreadtrum_flash), [pesquisa CVE](https://github.com/TomKing062/CVE-2022-38694_unlock_bootloader).
