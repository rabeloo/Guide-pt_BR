**Se o aparelho estiver travado na versão 2.1.0, leia as informações contidas [nesta](https://github.com/Haagenti/Guide-pt_BR/wiki/3DS-Travado-(2.1.0-Sem-Browser-Funcional)) página antes de tentar qualquer coisa. Elas podem evitar que você acabe com um 3DS inutilizável!**

O OTP é uma região única de cada console de onde presume-se que as chaves do sistema são derivadas, mesmo que não se saiba como.

O OTP é necessário para utilizar o arm9loaderhax que garante, além de outras coisas, boot com 100% de chance de sucesso, boot da RedNAND quase tão rápido quanto a SysNAND (utilizando algo como o Luma3DS) e acesso ao Arm9 logo ao ligar o console.

Desde a versão de firmware 3.0, o OTP é trancado logo quando a SysNAND é iniciada. Existe uma vulnerabilidade exclusiva do New 3DS que funciona na versão 9.6, mas ela requere equipamentos de hardware adicionais. A solução que usaremos é realizar o downgrade da RedNAND (para garantir que não realizaremos downgrades parciais) para a versão 2.1, e aí gravaremos a RedNAND na SysNAND para conseguirmos o OTP.

Se já possui a EmuNAND instalada, você pode seguir esta parte sem precisar trocar a instalação para RedNAND. Simplesmente leia todos os passos que envolvem a RedNAND como se referissem à EmuNAND.

Para mais informações técnicas sobre a OTP, leia [esta](https://github.com/Haagenti/Guide-pt_BR/wiki/Informações-sobre-o-OTP) página ou [este](https://3dbrew.org/wiki/OTP_Registers) artigo em inglês.

**O arquivo SecureInfo_A da RedNAND DEVE igual ao da SysNAND ou O 3DS SERÁ INUTILIZADO. Se a região da RedNAND foi trocada ou o arquivo SecureInfo_A foi modificado de qualquer forma, uma NOVA RedNAND DEVERÁ ser criada ou O 3DS SERÁ INUTILIZADO.**

**O downgrade DEVERÁ ser realizado com o pacote referente à região do console ou O 3DS SERÁ INUTILIZADO.**

*Se o aparelho estiver com ReiNand instalado, ele DEVERÁ estar na última versão (4.1 ou superior) ou o PlaiSysUpdater falhará 100% das vezes.*

**Se você estiver utilizando o Luma3DS e NÂO seguiu a Parte 3 deste guia anteriormente, você deverá copiar o arquivo `firmware.bin` apropriado ao seu console da Parte 3 para a pasta `/luma/` do cartão SD. Do contrário, o downgrade irá falhar.**

#### Resumo

O objetivo desta seção é realizar o downgrade para a versão de firmware 2.1.0 de modo a explorar uma vulnerabilidade para a extração do [OTP](https://github.com/Haagenti/Guide-pt_BR/wiki/Informações-sobre-o-OTP) único do console. Este arquivo é necessário para a instalação do arm9loaderhax e **não** pode ser utilizado em outros consoles que não o que realizou a extração o arquivo.

Para isso serão realizados backups da RedNAND e da SysNAND e então estas são preparadas para o downgrade. O downgrade é realizado colocando-se os arquivos de vários aplicativos necessários no cartão SD, injetando o FBI (um instalador de arquivos no formato CIA) e por fim formatando a RedNAND.

O processo de downgrade será realizado na RedNAND em vez da SysNAND, pois se algo der errado, a RedNAND pode ser facilmente restaurada a partir da SysNAND. O mesmo não pode ser feito se a falha ocorrer na SysNAND, o que inutilizaria o aparelho.

Antes de realizar o downgrade na RedNAND, primeiro é necessário formatá-la duas vezes (depois de realizar um backup). A formatação em si é realizada para evitar quaisquer conflitos com conteúdo instalado do usuário e deixar o processo todo mais seguro.

A formatação é realizada duas vezes em vez de uma porque a RedNAND e a SysNAND acabam por ficar ligadas caso elas tenham sido formatadas o mesmo número de vezes.

No caso da maioria dos usuários, como a Parte 3 do guia instrui a formatação da SysNAND, formatar a RedNAND aumentaria a contagem de formatações de cada NAND em um, o que faria com que as duas se ligassem novamente e lessem as informações de conteúdo da mesma pasta do cartão SD. Depois dos testes realizados pela comunidade homebrew, possuir as NANDs ligadas causou erros estranhos ao realizar o processo de downgrade para a versão 2.1.0. Por isso, a RedNAND é formatada uma segunda vez, fazendo assim com que as duas se desliguem.

Depois de realizado o preparo, é realizado o downgrade da RedNAND para o firmware 2.1.0 do 3DS Original. Depois, utiliza-se o OTPHelper, uma ferramenta também criada pelo [d0k3](https://github.com/d0k3/), para realizar o resto da configuração, chamada de "One Click Setup".

Esta configuração primeiro checa se o console em questão é um New 3DS e, em caso positivo, aplica alguns passos de ajuste (a troca de um cabeçalho da NAND e dos tipos de encriptação) para que o New 3DS consiga rodar um firmware exclusivo do 3DS Original (já que o New 3DS já sai de fábrica com o firmware 8.1.0).

Depois da checagem do New 3DS, a ferramenta verifica (em todas as versões do console) os hashes dos títulos de sistema da RedNAND para garantir que o downgrade foi realizado com sucesso antes de copiar a RedNAND para a SysNAND. Então são realizadas algumas checagens finais para garantir que tudo ocorreu corretamente e o sistema pode ser reiniciado.

Após iniciar o console no firmware 2.1.0, uma vulnerabilidade do kernel arm9 chamada ["2xrsa"](https://github.com/b1l1s/2xrsa) (feita pelo [Bilis](https://github.com/b1l1s)) é iniciada através do browser para rodar o OTPHelper e extrair o OTP único do console antes de restaurar a SysNAND para a versão 9.2.0 a partir de um backup realizado anteriormente.

#### Do que você precisa

* Uma RedNAND funcionando e um firmware modificado (você já deve ter isso se você concluiu a Parte 3)
* A última versão do [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* A última versão do [PlaiSysUpdater](https://github.com/Plailect/PlaiSysUpdater/releases/)
* A última versão do [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* A última versão do [OTPHelper](https://github.com/d0k3/OTPHelper/releases/)
* A última versão do [FBI](https://github.com/Steveice10/FBI/releases/)
* A última versão do [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* O arquivo zip com o firmware 2.1.0 referente ao aparelho e região:
 +    [New 3DS / 3DS Original ou 2DS 2.1.0 - EUR](https://mega.nz/#!MhcxXJKA!xcx62RvFiu7oKzCveqxUlDX1icv9UI-7BB1MoiWfn-Q) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDajdOM1QyQlhjRUk/view?usp=sharing))    
 +    [New 3DS / 3DS Original ou 2DS 2.1.0 - JAP](https://mega.nz/#!Ix9Fnb6Q!33ujhZnFLL48aY6mE_jEXuMFtCB7cugdg1eRH1geK94) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDYzBIckVEcW5IcW8/view?usp=sharing))   
 +    [New 3DS / 3DS Original ou 2DS 2.1.0 - USA](https://mega.nz/#!EpExwB6K!jfMSznN3_aT14N7LyM_BDBonBQz0mQTs0fx5pURoneU) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDWWtBODVzQWxpZ3c/view?usp=sharing))    

#### Instruções

Se a RedNAND / EmuNAND foi atualizada para a versão 11.0.0 ou superior, coloque o arquivo `firmware.bin` do NTR da Parte 5 na pasta `/luma/` do cartão SD *ou* restaure a RedNAND / EmuNAND a partir de um backup de uma versão anterior para conseguir realizar o downgrade. Isso acontece porque o FIRM da versão 11.0.0 não permite o downgrade.

##### Seção I - Preparação

1. **Agora é uma boa hora de usar um [gerenciador de saves](https://github.com/meladroit/svdt/releases) para realizar o backup de todos os saves de jogos instalados que você desejar guardar (realize dos passos 10 a 18 e depois instale o CIA do [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)) (apenas caso inesperadamente dê errado)**
2. Extraia as pastas `OTPHelper` do arquivo zip do OTPHelper e `Decrypt9WIP` do arquivo zip do Decrypt9 zip para a pasta `/3ds/` do cartão SD
3. Extraia os arquivos `PlaiSysUpdater.cia` do arquivo zip do PlaiSysUpdater, `TinyFormat.cia` do arquivo zip do TinyFormat, e os arquivos `arm11.bin` e `arm9.bin` do arquivo zip do OTPHelper para a raiz do cartão SD
5. Reinsira o cartão SD no 3DS e inicie a RedNAND utilizando qualquer firmware modificado (se você seguiu a Parte 3 deste guia, isto pode ser feito iniciando o Luma3DS a partir do Homebrew Launcher)
11. **CERTIFIQUE-SE DE QUE O APARELHO ESTÁ NA RedNAND (SE VOCÊ SEGUIU A PARTE 3 DESTE GUIA, CERTIFIQUE-SE DE QUE A PALAVRA "EMU" APARECE NA FRENTE DA VERSÃO DO SISTEMA NAS CONFIGURAÇÕES)**
10. Atualize a **RedNAND** para a última versão utilizando as configurações do sistema caso a mesma já não esteja atualizada (**NÃO ENTRE NO MENU DE GERENCIAMENTO DE DADOS DO CARTÃO SD OU SAIA DO APLICATIVO DE CONFIGURAÇÕES DO SISTEMA JÁ QUE ISTO FARÁ O SISTEMA REINICAR NA SYSNAND**)	
9. **Certifique-se de que a conexão WiFi está ligada (não foi desabilitada pelas configurações de sistema da SysNAND). Caso contrário, você poderá ligá-la novamente retirando a bateria do console por alguns segundos e reinserindo-a**
10. Abra o Homebrew Launcher através da SysNAND por meio da entrada de sua escolha
11. Abra o Decrypt9 **(várias tentativas podem ser necessárias)**, acesse a opção "EmuNAND Options" e depois "Health & Safety Dump" para extrair o aplicativo Health & Safety para `hs.app` **(você pode utilizar os botões Cima e Baixo / Esquerda e Direita para mudar o nome)**
12. Pressione Select para ejetar o cartão SD, depois coloque-o em seu computador
13. Extraia o Universal Inject Generator para alguma pasta de seu computador e copie os arquivos `hs.app` do SD e `FBI.cia` do arquivo zip do FBI para a pasta `input`
14. Clique duas vezes em `go.bat` *(ou execute o arquivo `go.sh` no Terminal do Linux / Mac)*
15. Copie o arquivo `FBI_inject_with_banner.app` para a raiz do cartão SD e reinsira o cartão SD no 3DS
16. Aperte B no Decrypt9, então entre em "EmuNAND Options" e selecione a opção "Health & Safety Inject"
17. Aperte Baixo uma vez para selecionar o arquivo `FBI_inject_with_banner.app`, e pressione A
18. Volte para o menu principal e aperte Start para reiniciar
19. Inicie no Homebrew Launcher pela SysNAND através da entrada de sua escolha
20. Abra o OTPHelper
21. Entre em "NAND Backup & Restore"
22. Realize backup da RedNAND para `emuNAND_original.bin` **(você pode usar os botões Cima e Baixo / Esquerda e Direita para mudar o nome do arquivo)**
23. Entre nas opções da SysNAND no menu principal
24. Realize um backup da SysNAND para o arquivo `sysNAND_original.bin`
25. Pressione Select no menu principal para ejetar o cartão SD
26. Coloque o cartão SD em seu computador e copie os arquivos `sysNAND_original.bin` e `emuNAND_original.bin` para uma pasta segura em seu computador, você precisará destes arquivos no futuro **(Os backups deverão possuir algum dos tamanhos citados [nesta](https://github.com/Haagenti/Guide-pt_BR/wiki/Tamanhos-de-NAND) página. Caso contrário, delete-os e realize novos backups!)**
27. Delete o arquivo `emuNAND_original.bin` (se o cartão SD sendo utilizado possuir pouco espaço, também delete o arquivo `sysNAND_original.bin`)
28. Reinsira o cartão SD no 3DS, aperte Start e Direita ao mesmo tempo para reiniciar e depois inicie a RedNAND utilizando qualquer firmware modificado (se você seguiu a Parte 3 do guia, você pode fazer isso iniciando o Luma3DS através do Homebrew Launcher)
29. Inicie o aplicativo Health and Safety (que agora é o FBI) na RedNAND
30. Navegue até o arquivo `TinyFormat.cia` e pressione A para instalar
31. Aperte o botão Home para sair do FBI e execute o TinyFormat através do novo ícone instalado no menu inicial
32. Pressione Y para formatar a **RedNAND**
33. Reinicie o console na RedNAND e complete as configurações iniciais do sistema *sem* efetuar login com o Nintendo Network ID
34. **Repita os passos 29 até 33. Isto **não** é opcional (em outras palavras, você deverá usar o TinyFormat para formatar a RedNAND duas vezes - se não o fizer, o console poderá ficar inutilizável após realizar o downgrade)**
35. Remova quaisquer modificações feitas no TWL do console ou o PlaiSysUpdater irá retornar um erro      
(se você não tem ideia do que isso significa, não se preocupe. Grande parte dos usuários não precisa realizar este passo)
36. Inicie o aplicativo Health and Safety Application (que agora é o FBI)
37. Navegue até o arquivo `PlaiSysUpdater.cia` e pressione A para instalar

##### Seção II - Downgrade
1. Reinicie o console na SysNAND e inicie o Homebrew Launcher através da entrada de sua escolha
2. Abra o OTPHelper, selecione a opção "NAND Backup and Restore" e depois "EmuNAND Backup"
3. Realize o backup da RedNAND para `emuNAND_formatted.bin`
4. Pressione Select no menu principal para ejetar o cartão SD
5. Insira o cartão SD em seu computador e copie o arquivo `emuNAND_formatted.bin` para uma pasta segura em seu computador
6. Delete quaisquer pastas `updates` do cartão SD que possam existir de downgrades ou updates anteriores
7. Extraia a pasta `updates` do arquivo zip do firmware 2.1.0 para a raiz do cartão SD
8. Reinsira o cartão SD no 3DS, pressione Start e Direita ao mesmo tempo para reiniciar, e inicie o 3DS na RedNAND utilizando qualquer firmware modificado
9. Abra o PlaiSysUpdater **na RedNAND**
10. Pressione X para realizar o downgrade da RedNAND para a versão 2.1.0
  + **Se for exibido um erro ao realizar o downgrade relacionado ao NFIRM, certifique-se de que você leu a seção superior à parte "Resumo" e realizou todas as instruções relevantes**
11. Se você encontrar um erro em qualquer ponto durante o downgrade, restaure o backup `emuNAND_formatted.bin` da RedNAND iniciando a SysNAND e utilizando o OTPHelper através do Homebrew Menu. Depois, você pode tentar novamente o downgrade na RedNAND, restaurando novamente o backup até que o downgrade finalize sem erros. *Este downgrade pode precisar de várias tentativas até que tudo dê certo. Continue tentando até que tudo funcione corretamente*     
12. **A RedNAND estará inutilizável após o downgrade se você estiver utilizando um New 3DS, mas você não conseguirá iniciá-la de qualquer maneira, já que nenhum firmware modificado até o momento consegue iniciar uma RedNAND na versão 2.1.0 (uma tela preta ao tentar iniciar a RedNAND é normal)**
13. Reinicie o console na SysNAND, e depois inicie o Homebrew Launcher através da entrada de sua escolha
14. Abra o OTPHelper
15. Selecione a opção "One Click Setup" e confirme (caso seja perguntado, não há a necessidade de se realizar um novo backup. Certifique-se de que o backup feito anteriormente foi guardado em algum lugar seguro de seu compudador, ele **será necessário** posteriormente). Isto pode demorar algum tempo.         
**(Se o processo falhar ou retornar algum erro, NÃO SIGA EM FRENTE ou você pode INUTILIZAR O APARELHO. Você deverá [seguir este guia de resolução de problemas](https://github.com/Haagenti/Guide-pt_BR/wiki/Resolução-de-Problemas#ts_otphelper_verify_fail))**
16. Cruze os dedos
17. Reinicie o aparelho
18. Ao iniciar, se o aparelho travar em uma tela preta, reinicie com o cartão SD inserido, remova-o e depois reinsira quando o menu inicial aparecer. Se isto também falhar, [siga este guia de resolução de problemas](https://github.com/Haagenti/Guide-pt_BR/wiki/Resolução-de-Problemas#ts_sys_down)

##### Seção III - Extraindo o OTP

*(É normal que a tela aparente estar esticada no 2DS rodando a versão 2.1.0)*

1. Abra o browser do 3DS e vá até `http://dukesrg.github.io/2xrsa.html?arm11.bin`
2. O OTPHelper será iniciado. Selecione a opção "Dump otp.bin (0x100)"
3. Pressione Select no menu principal para ejetar o cartão SD
4. Coloque o cartão SD em seu computador e copie o arquivo `otp.bin` para uma pasta segura do computador		
5. Verifique se o arquivo `otp.bin` possui 256 bytes
6. Faça backup do arquivo `otp.bin` em múltiplos locais (como armazenamento online)

##### Seção IV - Restaurando o Sistema
1. Copie o arquivo de backup `sysNAND_original.bin` feito na Seção I para a raiz do cartão SD
2. Reinsira o cartão SD no 3DS e pressione B para retornar ao menu principal
3. Selecione a opção "NAND Backup & Restore"
4. Restaure a SysNAND do arquivo `sysNAND_original.bin`
5. Cruze os dedos
6. Reinicie o sistema!
