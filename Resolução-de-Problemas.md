Se o aparelho não liga, procure a seção que for relevante a você e siga as instruções. A partir do momento que uma solução funcionar, você poderá continuar seguindo o guia principal.

(Esta seção é relativamente longa, utilize a função de busca do navegador para procurar pelo problema.)

**Se você ainda não conseguir resolver o problema e necessita de ajuda, faça upload de todos os arquivos .log relevantes da raiz do cartão SD no site [Up1](https://up1.ca/) e volte preparado com uma descrição detalhada do problema e do que você já tentou fazer para resolvê-lo.**

## <a name="ts_safe_a9lh" />O console é iniciado diretamente no SafeA9LHInstaller
Você copiou o arquivo `arm9loaderhax.bin` errado para o cartão SD (você deveria apenas ter extraído a pasta `3ds` e o arquivo `SafeA9LHInstaller.dat` a partir do zip do SafeA9LHInstaller).

1. Utilize o arquivo `arm9loaderhax.bin` correto
   1. Extraia o arquivo `arm9loaderhax.bin` do arquivo zip do Luma3DS para a raiz do cartão SD
   2. Reinicie o console segurando o botão Select e continue

## <a name="ts_bs_rednand" />Tela preta ao tentar iniciar a RedNAND

1. Tente resetar as configurações do Luma3DS e corrija as opções
   1. Delete o arquivo `/luma/config.bin` do cartão SD
   2. Reconfigure as opções ao iniciar
2. Restaure a RedNAND a partir de um backup. *(Se você seguiu o guia corretamente, você já deve ter um backup)*

## <a name="ts_otphelper_verify_fail" />O OTPHelper não consegue verificar minha NAND

Siga os passos referentes ao erro que estiver aparecendo.

####"FIRM0 hash mismatch!"

1. **PARE! NÃO FAÇA MAIS NADA. REIICIAR O SISTEMA AGORA PODE DEIXÁ-LO INUTILIZÁVEL SE UM FIRM INCORRETO FOI INSTALADO NA SYSNAND**
2. Baixe o [firm.bin 2.1.0](https://mega.nz/#!R0NHBBhZ!R8EjGr9aL5iL_OFoGmDpXxtoIk4bLlFxE68ioo4zLEQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVm55N1dhNmsyZjQ/view?usp=sharing))
3. No 3DS, pressione B até retornar ao menu principal
4. **Cuidadosamente** pressione o botão **SELECT** para ejetar o cartão SD
5. **SEM DESLIGAR O 3DS,** retire o cartão SD e coloque-o em seu computador
6. Copie o arquivo `firm.bin` para a raiz do cartão SD
7. Reinsira o cartão SD no 3DS
8. Pressione **B** até retornar ao menu principal
9. Selecione a opção "FIRM Dump & Inject..."
10. Selecione a opção "EmuNAND FIRM0 Inject" e depois o arquivo `firm.bin`
11. Selecione a opção "EmuNAND FIRM1 Inject" e depois o arquivo `firm.bin`
12. Pressione o B até retornar ao menu principal
13. Selecione a opção "One Click Setup"
14. Se após executar estes passos ainda existir erro, restaure a SysNAND a partir do backup `sysNAND_original.bin`, restaure a RedNAND a partir do arquivo `emuNAND_formatted.bin` e recomece a partir da Parte 4 - Seção II - Passo 9.

####"Validation Stage 1: FAILED" e "Validation Stage 2: FAILED"  

**ESTES PASSOS APLICAM-SE APENAS A ERROS RELACIONADOS A ARQUIVOS .TMD E NÃO A ERROS COM ARQUIVOS .APP**    
**Se você estiver tendo algum problema relacionado a arquivos .app, você deve restaurar a SysNAND a partir do arquivo `sysNAND_original.bin`, a RedNAND a partir do arquivo `emuNAND_formatted.bin` e tentar novamente a partir da Parte 4 - Seção II - Passo 9.**

1. Verifique o arquivo `otphelper.log` e cheque quais títulos falharam na verificação de hash TMD
2. Baixe a última versão do [GodMode9](https://github.com/d0k3/GodMode9/releases)
3. Extraia a pasta `GodMode9` do arquivo zip `GodMode9` para a pasta `/3ds/` na raiz do cartão SD
4. Inicie o Homebrew Launcher na SysNAND através da entrada de sua escolha
5. Inicie o GodMode9 **(Tenha MUITO cuidado com esta ferramenta, ela pode inutilizar o aparelho se você deletar algo importante com ela)**
6. Selecione a opção (na tela inferior) `emuNAND CTRNAND`
7. Selecione `title`
8. Selecione a pasta que possuir os mesmos 8 carateres do começo do título que falhou na verificação de hashes *(por exemplo, se a falha na verificação aconteceu depois da mensagem `Checking title 0004013000003202...` então você deve selecionar a pasta `00040130`)*
9. Selecione a pasta que possuir os mesmos 8 carateres do fim do título que falhou na verificação de hashes *(por exemplo, se a falha na verificação aconteceu depois da mensagem `Checking title 0004013000003202...` então você deve selecionar a pasta `00003202`)*
10. Selectione `content`

The latest release of OTPHelper rarely shows false positives, but if you want to you can check manually just to be sure. To do this, press A on each .tmd and select "Calculate SHA-256" to manually compare to see if at least one of the `.tmd` files in each folder match a Sha256Sum to [this list](https://gist.github.com/Plailect/a6789c6a87a2eee575da).

A última versão do OTPHelper raramente exibie falsos positivos, mas se você quiser, você pode checar manualmente só para ter certeza. Para fazer isso, pressione o botão A em cada arquivo .tmd, selecione "Calculate SHA-256" e verifique manualmente se pelo menos um dos arquivos .tmd de cada pasta bate com um valor Sha256 [desta lista](https://gist.github.com/Plailect/a6789c6a87a2eee575da).

Se em cada pasta **pelo menos um** dos arquivos `.tmd` bate com um dos hashes da lista, um falso positivo ocorreu e você pode seguir os seguintes passos. **Se o aparelho é um New 3DS você deverá consertar a EmuNAND primeiro.** Selecione a opção "NAND Backup & Restore" -> "Clone RedNAND to SysNAND", selecione "NAND Validation Options" -> "Validate SysNAND Downgrade" e confirme se a SysNAND possui o mesmo erro da RedNAND. **Se um NOVO erro aparecer após clonar a RedNAND para a SysNAND, restaure a SysNAND a partir do arquivo `SysNAND_original.bin`, restaure a RedNAND a partir do arquivo `emuNAND_formatted.bin` e reinicie a partir da Parte 4 - Seção II - Passo 9.** Se não aparecer um erro NOVO, continue a seguir o guia, ignorando o erro.

Se, em qualquer pasta, **nenhum** dos arquivos `.tmd` bater, este foi um erro de downgrade legítimo. Restaure a RedNAND a partir do arquivo `emuNAND_formatted.bin` e reinicie a partir da Parte 4 - Seção II - Passo 9

Verifique todos os títulos que retornaram erro de checagem de hash com este método.

####"Validation Stage 1: SUCCESS" e "Validation Stage 2: FAILED"

Isso acontece quando a NAND está fragmentada (problema causado por vários motivos como a injeção problemática do FBI feita pelo rxTools ou softwares do Gateway). O OTPHelper não consegue verificar os arquivos de uma NAND fragmentada, mas se a mensagem "Validation Stage 1: SUCCESS" aparece e depois "Validation Stage 2: FAILED", isto raramente é algo que não um falso positivo.

Você pode seguir em frente e gravar a imagem na SysNAND por conta e risco. Caso não se sinta seguro você pode tentar desfragmentar a NAND utilizando o Decrypt9 para extrair a partição CTRNAND, montá-la em seu computador utilizando algo como o [OSFMount](http://www.osforensics.com/tools/mount-disk-images.html) e depois desfragmentá-la utilizando algo como o [Defraggler](https://www.piriform.com/defraggler/download/standard).

## <a name="ts_otp_helper" />O OTPHelper / Decrypt9 não consegue restaurar / encontrar meu backup de NAND

1. Certifique-se de que existe uma pasta chamada `Decrypt9` na **raiz** do cartão SD
2. Baixe novamente e recopie os arquivos do OTPHelper
3. Tente verificar sistema de arquivos do cartão SD com algo como `fsck.vfat <caminho da partição do cartão>` (no *nix) ou `CHKDSK <letra do cartão SD> /F` (no Windows)
4. Tente realizar backup dos arquivos do cartão Sd, formate-o e copie os arquivos de volta
5. Tente utilizar um cartão SD diferente

## <a name="ts_sys_down" />Tela preta ao iniciar a SysNAND após realizar downgrade

1. Tente ligar o aparelho sem o cartão SD e depois reinsira-o após o início do sistema.
   1. Segure o botão power para desligar o 3DS.
   2. Retire o cartão SD.
   3. Ligue o 3DS.
   4. Quando o menu inicial aparecer, reinsira o cartão SD.
2. Se você possui um hardmod e um backup da NAND backup, tente gravar o backup de volta na SysNAND.
3. Tente reiniciar no modo de recuperação e atualize o sistema.    
   *Isso provavelmente não funcionará em aparelhos 3DS Original no firmware 2.1.0*    
   **Isso irá INUTILIZAR qualquer aparelho New 3DS no firmware 2.1.0**
   1. Segure o botão power para desligar o 3DS.
   2. Segure L+R+A+Cima.
   3. Ligue 3DS.
   4. Se você entrar no modo de recuperação, atualize o 3DS *apeanas se você possui uma entrada que funcione na última versão de firmware* e tente realizar downgrade novamente.
4. O 3DS pode estar inutilizável. Para ajuda, contate algum operador do canal [#3dshacks no Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4) (em inglês).

## <a name="ts_sys_a9lh" />Tela preta ao iniciar a SysNAND depois de instalar o arm9loaderhax

1. Verifique se você possui um pacote funcional.
   1. Verifique se o arquivo `arm9loaderhax.bin` existe na raiz do cartão SD.
   2. Verifique se
      1. O arquivo `/luma/firmware.bin` existe; e
      2. Se o arquivo`/luma/firmware.bin` é da versão correta para o aparelho.
2. Tente resetar as configurações do Luma3DS e corrija as opções
   1. Delete o arquivo `/luma/config.bin` do cartão SD
   2. Reconfigure as opções ao iniciar
2. Tente iniciar o Decrypt9
   1. Segure Start ao ligar o aparelho
3. Tente utilizar o [pacote de testes](https://mega.nz/#!YxMiGDhB!VZLv2XPSqFFzEhf4kGMXAdQtSpIGvnp2vu2W1j4o7cc/) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDanVaR3FTUTFqNFU/view?usp=sharing)).
   1. Renomeie o arquivo `/arm9loaderhax.bin`, caso exista, para qualquer outra coisa.
   2. Extraia o arquivo `arm9loaderhax.bin` a partir do arquivo acima para a raiz do cartão SD.
   3. Insira o cartão SD no 3DS e ligue-o.
   4. Pressione A. O aparelho deverá desligar. Isto significa que o arm9loaderhax está funcionando, mas alguma outra coisa está desconfigurada ou não está funcionando. O aparelho **não** está inutilizável.
4. O 3DS pode estar inutilizável. Para ajuda, contate algum operador do canal [#3dshacks no Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4) (em inglês).

## <a name="ts_sys_blue" />Tela azul ao iniciar (erro na bootrom)

1. O 3DS está inutilizável.
2. Você precisará de um [hardmod](https://gbatemp.net/threads/414498/) (link em inglês). Caso contrário leve a uma autorizada da Nintendo para que o aparelho seja consertado / trocado.