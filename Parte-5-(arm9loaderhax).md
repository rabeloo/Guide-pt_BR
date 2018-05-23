#### A opção de instalação do CakesFW foi removida pela falta de foco de seu desenvolvedor e pela [baixa popularidade](http://i.imgur.com/zoKDiD1.png).

(se o CakesFW realmente for apropriado para você, você pode instalá-lo sem a ajuda deste guia)

**Utilizar o arquivo OTP gerado em outro console para esta seção fará com que o 3DS seja INUTILIZADO. Utilize apenas arquivos gerados no próprio aparelho.**

Este passo final do guia tem como objetivo instalar o arm9loaderhax e configurar o Luma3DS para iniciar milissegundos após o boot. Isso é possível graças ao aplicativo SafeA9LHInstaller, feito pela [AuroraWright](https://github.com/AuroraWright/).

Este guia instalará o [Fork do Delebile](https://github.com/delebile/arm9loaderhax) do arm9loaderhax.

**Se você atualmente possui a SysNAND Atualizada + CakesFW e gostaria de trocar para a SysNAND Atualizada + Luma3DS, basta seguir a parte "Preparação".**

Este guia utiliza o modo "Updated SysNAND" (SysNAND Atualizada), no qual copiamos a RedNAND para a SysNAND (mantendo todos os jogos, etc.) e instalamos o arm9loaderhax para obter uma SysNAND permanentemente hackeada, de modo que a RedNAND não seja mais necessária.

Também será configurada uma maneira para iniciar outros aplicativos direto do arm9loaderhax, logo ao ligar o aparelho. Isso permite que possamos corrigir e restaurar a SysNAND a partir de backups em situações que normalmente tornariam o 3DS inutilizável.

#### Resumo

Esta seção tem como objetivo guiá-lo através do processo final: a instalação do arm9loaderhax.

Este é praticamente o melhor tipo de vulnerabilidade do console, pois é instalável permanentemente nas partições FIRM da NAND e é executado logo antes da maioria do resto do sistema operacional. Isto permite que a vulnerabilidade funcione em *todas* as versões depois de instalada, como também permitir que o console possa ser restaurado de quase todas as situações que fariam com que um console sem arm9loaderhax ficasse inutilizável.

Após a instalação do pacote utilizando o OTP único do console conseguido na Parte 4, será instalado um firmware modificado que faz uso desta vulnerabilidade. O arquivo `arm9loaderhax.bin` é o que será carregado pelo próprio arm9loaderhax depois que ele termina de iniciar a partir da NAND. Este arquivo pode ser qualquer pacote de código arm9 válido e pode ser trocado a qualquer momento, mas isso não se fará necessário já que o Luma3DS permite que outros pacotes arm9 sejam iniciados após segurar certas combinações de botões após ligar o console.

Neste caso, será utilizado o Luma3DS (feito pela [AuroraWright](https://github.com/AuroraWright/)) para iniciar uma SysNAND modificada diretamente, retirando a necessidade de qualquer tipo de RedNAND e simplificando muito o uso do 3DS hackeado (além de economizar espaço no cartão SD).

Depois que o arm9loaderhax é instalado e o Luma3DS é configurado corretamente, é feito um backup do cartão SD e o mesmo é formatado com o EmuNAND9 para remover a RedNAND obsoleta e recuperar o espaço do cartão SD.

Durante este procedimento, também serão instalados aplicativos como: **FBI** *(instalador de jogos e aplicativos em formato CIA)*, **Luma3DS Updater** *(atualiza a instalação do Luma3DS facilmente)*, **Uncart** *(converte jogos em cartucho para arquivos CIA)*, **Decrypt9** *(permite a restauração da NAND antes do início do sistema de modo a permitir a restauração de sistemas inutilizados)* e **EmuNAND9** *(gerencia a instalação da RedNAND)*.

#### Do que você precisa

* [data_input.zip](https://mega.nz/#!Qkth0BoI!pDgWMamN5cu6HZ91j238MNh7q5ROQKq-a6NLC7Q0dhU) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZUVfWkJkYlM1UEU/view?usp=sharing))
* [payload_input.zip](https://mega.nz/#!YhNRVZAB!Dyx315T174kdy9E3IyOfeXEek-L8262BJnozHHMcez4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRjh1eXZDRmhXWUk/view?usp=sharing))
* [slotkey_input.zip](https://mega.nz/#!R0VQGDLJ!LIUoz_ErqmbXpOO2cBsmyG6KGCgBdR5xjOg7EPci5Ao) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDN0ZaTjFfQkpNc3M))
* A última versão do [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* A última versão do [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* A última versão do [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* A última versão do [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* A última versão do [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* A última versão do [Uncart para arm9loaderhax](https://github.com/AuroraWright/uncart/releases)
* A última versão do [Luma3DS Updater](http://3ds.intherack.com/files/lumaupdate_1.2.0.cia)
* *New 3DS:*
    + O arquivo zip do [firmware bin do NTR para o Luma3DS](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing))
    + O pacote do Homebrew Launcher para o firmware 11.0.0 para a sua região:
        + [New 3DS - EUR](https://mega.nz/#!BwsB3ApC!T495cC4EoG74BxKuqxSeCr6xpToYT2IdtCbnbazx6ds) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDWjR2aHg2NEtZX3c))
        + [New 3DS - JPN](https://mega.nz/#!w9c2WIIB!TJtxWqENoid5evPZaZnvh0uAyfeRinR-167_9TFuAgE) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdnV4QWl4VzJveWs))
        + [New 3DS - USA](https://mega.nz/#!Y5FQFLwZ!aYqnCSB5hZcscObePMcN_1oJ8l70zPcMVI86XRFmnYM) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDY0s1Y0dTMXhieDA))
* *3DS Original / 2DS:*
    + O arquivo zip do [firmware bin do NTR para o Luma3DS](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing))
    + O pacote do Homebrew Launcher para o firmware 11.0.0 para a sua região:
        + [3DS Original - EUR](https://mega.nz/#!go1XRRoK!CRUBgEAV5gAA95W3bK8yi78mRacXtANXrpUKrJOFCIA) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDcHliR0QxeTdBcUE))
        + [3DS Original - JPN](https://mega.nz/#!RpFyGIbZ!IYjVxnSu33-kL28riaC5SoBR_f832QlgvNKmA721Vhc) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDT0JkMVpYZmc2T0k))
        + [3DS Original - USA](https://mega.nz/#!R1tGQKhK!Xi7IvjULTVzAkNU3s0opGtGbWLY_clL00BoCwQqk-Zo) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZ3NMZURLa01lbTA))

#### Instruções

##### Seção I - Preparação

1. Delete a pasta `Decrypt9` da raiz do cartão SD caso a mesma exista
2. Delete a pasta `EmuNAND9` da raiz do cartão SD caso a mesma exista
2. Extraia a pasta `a9lh` do arquivo `data_input.zip` para a raiz do cartão SD
3. Extraia e sobrescreva a pasta `a9lh` do arquivo `payload_input.zip` para a raiz do cartão SD
4. **Copie o arquivo `OTP.bin` específico do console (obtido após a Parte 4) para a pasta `/a9lh/` na raiz do cartão SD**
5. Extraia e sobrescreva a pasta `3ds` do arquivo zip do SafeA9LHInstaller para a raiz do cartão SD
6. Extraia o arquivo `SafeA9LHInstaller.dat` do arquivo zip do SafeA9LHInstaller para a raiz do cartão SD
7. Extraia o arquivo `hblauncher_loader.cia` do arquivo zip do hblauncher_loader para a raiz do cartão SD
4. Copie o arquivo `lumaupdate_1.2.0.cia` para a raiz do cartão SD
8. Extraia o arquivo `arm9loaderhax.bin` e a pasta `luma` do arquivo zip do Luma3DS para a raiz do cartão SD
9. Extraia o arquivo `Decrypt9WIP.bin` do arquivo zip do Decrypt9WIP para a pasta `/luma/payloads/` do cartão SD
10. Na pasta `/luma/payloads`, renomeie o arquivo `Decrypt9WIP.bin` para `start_Dec9.bin`
11. Extraia e sobrescreva a pasta `3DS` do arquivo zip do EmuNAND9 para a raiz do cartão SD
12. Extraia o arquivo `EmuNAND9.bin` do arquivo zip do EmuNAND9 para a pasta `/luma/payloads/` do cartão SD
13. Na pasta `/luma/payloads`, renomeie o arquivo `EmuNAND9.bin` para `y_EmuN9.bin`
14. Extraia o arquivo `arm9loaderhax.bin` do arquivo zip do Uncart para a pasta `/luma/payloads/` no cartão SD
15. **Na pasta `/luma/payloads`, renomeie `arm9loaderhax.bin` para `x_Uncart.bin`**
16. Extraia o conteúdo do arquivo `slotkey_input.zip` para a raiz do cartão SD
17. Extraia o arquivo `firmware.bin` do arquivo zip do firmware NTR para Luma3DS para a pasta `/luma/` do cartão SD
4. **Extraia o arquivo zip do pacote do Homebrew Launcher para o firmware 11.0.0 para a sua região para a raiz do cartão SD**
18. Copie o arquivo de backup `emuNAND_original.bin` feito na Seção I da Parte 4 para a raiz do cartão SD

##### Seção II - Instalando o arm9loaderhax

1. Reinsira o cartão SD no 3DS
2. Inicie o Homebrew Launcher através da entrada de sua escolha
3. Inicie o SafeA9LHInstaller
5. Selecione a opção "Full Install"
6. O instalador irá instalar o arm9loaderhax no aparelho (isso é bem rápido)
7. Segure Select para iniciar o console no menu de configuração do Luma3DS.     
  + Se for apresentada apenas uma tela preta, [siga este guia de resolução de problemas](https://github.com/Haagenti/Guide-pt_BR/wiki/Resolução_de_Problemas#ts_sys_a9lh).    
  + Se o console iniciar no SafeA9LHInstaller, [siga este guia de resolução de problemas](https://github.com/Haagenti/Guide-pt_BR/wiki/Resolução_de_Problemas#ts_safe_a9lh).

##### Seção III - Configurando o Luma3DS

1. Utilize o botão A e o direcional para ligar as seguintes opções:    
 + "Autoboot SysNAND"
 + "SysNAND is updated"
 + "Force A9LH detection"
 + "Show current NAND in System Settings"
 + "Show GBA boot screen in patched AGB_FIRM"
2. Se você estiver utilizando um New 3DS você poderá *também*:
 + Mudar a opção "New 3DS CPU" para "Clock+L2(x)" de modo a melhorar a performance em alguns jogos
3. Pressione Start para salvar e reiniciar

##### Seção IV - Copiando os dados da RedNAND para a SysNAND

1. Reinicie o aparelho e inicie Decrypt9 a partir do arm9loaderhax segurando Start ao ligar
2. Selecione a opção "SysNAND Options"
3. Selecione a opção "SysNAND Backup/Restore..."
4. Selecione a opção "NAND Restore **(keep a9lh)**"
5. Confirme e restaure a SysNAND a partir do arquivo `emuNAND_original.bin`

##### Seção V - Removendo a RedNAND do cartão SD

1. Pressione Select no menu principal para ejetar o cartão SD
2. Delete o arquivo `emuNAND_original.bin` da raiz do cartão SD
3. **Faça backup de TODOS os arquivos que estiverem no cartão SD para uma pasta em seu computador. Todos os arquivos serão deletados no passo a seguir**    
(se você seguiu a Parte 3 deste guia, você pode deletar o backup anterior do cartão SD - este backup irá substituí-lo)
4. Reinsira o cartão SD no 3DS.
5. Segure o botão Y ao ligar o sistema para iniciar o EmuNAND9
6. Selecione a opção "SD Format Options" e depois "Format SD..."
7. Selecione a opção "Format SD (No EmuNAND)"
7. Ignore a mensagem e continue
8. Pressione Select no menu principal para ejetar o cartão SD
9. Coloque o cartão SD em seu computador e copie todos os arquivos do backup do passo 3 de volta

##### Seção VI - Finalizando a configuração

1. Reinsira o cartão SD no 3DS
1. Do menu "EmuNAND Manager Options", faça um backup da SysNAND para o arquivo `sysNAND.bin`
2. Pressione Select no menu principal para ejetar o cartão SD e coloque-o em seu computador
3. Renomeie o arquivo `sysNAND.bin` para `sysNAND-A9LHAX.bin` e copie-o para algum lugar seguro de seu computador. Isto é um backup da SysNAND com o arm9loaderhax instalado **(O backup deve possuir o mesmo tamanho de algum dos tamanhos citados [nesta](https://github.com/Haagenti/Guide-pt_BR/wiki/Tamanhos-de-NAND) página. Caso contrário, você deve deletá-lo e realizar um novo backup!)**
4. Delete o arquivo `sysNAND-A9LHAX.bin` do cartão SD
5. Reinsira o cartão SD no 3DS e pressione Start para reiniciar
6. Atualize a sua SysNAND com firmware modificado para a última versão utilizando as configurações do sistema (se já não estiver atualizada)
7. Abra o aplicativo Health and Safety (que agora é o FBI)
7. Selecione a opção "SD"
8. Navegue até o arquivo `hblauncher_loader.cia` e pressione A para instalar
9. Navegue até o arquivo `lumaupdate_1.1.2.cia` e pressione A para instalar
9. Saia do aplicativo com o botão Home
10. Abra o Homebrew Launcher a partir do ícone no menu inicial pelo menos uma vez para baixar o pacote de instalação

Se tudo seguiu de acordo com o plano, o arm9loaderhax foi instalado no aparelho, a RedNAND foi copiada para a SysNAND e posteriormente deletada, você possuirá um instalador de arquivos CIA e você poderá iniciar o Homebrew Launcher a partir do menu inicial do 3DS. O console automaticamente iniciará a SysNAND com o Luma3DS.

Agora você poderá usar o aplicativo Luma3DS Updater para atualizar o Luma3DS para a última versão. Basta iniciá-lo e apertar A. *(Isto não é o mesmo que uma atualização de sistema/firwmare. Isto apenas fará o download dos arquivos da última versão do Luma3DS)*

Não será mais possível ligar o console sem o cartão SD inserido, isso é normal.    
O Luma3DS será iniciado a partir da SysNAND por padrão.    
Segure o botão Select ao ligar o console para iniciar o menu de configuração do Luma3DS.    
Segure o botão Start ao ligar o console para iniciar o Decrypt9, uma ferramenta completa para gerenciamento de NAND.    
Segure o botão Y ao ligar o console para iniciar o EmuNAND9, uma ferramenta completa para gerenciamento da RedNAND e do cartão SD.    
Segure o botão X ao ligar o console para iniciar o Uncart, uma ferramenta para [converter um jogo de cartucho](https://www.reddit.com/r/3dshacks/comments/4hwuhf/) para um arquivo instalável. (no guia do link, em inglês, substitua todas as citações de "Brahma" por "arm9loaderhax")      
Você pode remover quaisquer arquivos extra da raiz do SD que não estiverem na imagem abaixo.

![Cartão SD](http://i.imgur.com/jdJxrKY.png)