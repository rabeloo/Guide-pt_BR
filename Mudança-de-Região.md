Esta é uma seção adicional para mudar a região da SysNAND com o arm9loaderhax e um firmware modificado já instalados. Isso é feito instalando CIAs que injetam um arquivo SecureInfo_A para a região que você quer trocar.

**Você DEVE já ter completado a Parte 5 e instalado o arm9loaderhax + Luma3DS. Caso contrário, o 3DS FICARÁ INUTILIZÁVEL.**

**Você DEVE ter backups funcionais da SysNAND após a instalação do arm9loaderhax (como `sysNAND-A9LHAX.bin`) caso algo de errado aconteça.**

Este método de troca de regiões não suporta o acesso à eShop, mas o guia será atualizado assim que se saiba de algum que permita.

Fique avisado de que a troca de regiões é experimental e pode quebrar várias coisas no sistema.

A troca de regiões é praticamente desnecessária, já que o Luma3DS agora suporta a instalação de jogos de qualquer região e, para cada jogo, é possível realizar a [emulação de região individual](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage) (link em inglês).

#### Do que você precisa

* Um editor hexadecimal; Os seguintes são recomendados
    - Windows: [HxD](https://mh-nexus.de/en/hxd/)
    - Mac: [Hex Fiend](http://ridiculousfish.com/hexfiend/)
    - Linux: [Bless](http://home.gna.org/bless/index.html)
* A última versão do [sysUpdater](https://github.com/profi200/sysUpdater/releases)
* A última versão do [FBI](https://github.com/Steveice10/FBI/releases)
* A última versão do [GodMode9](https://github.com/d0k3/GodMode9/releases)
* O arquivo zip com o firmware 9.2.0 referente ao aparelho e à região para qual você deseja trocar:    
**Perceba que os pacotes para o New 3DS 9.2.0 não são os mesmos utilizados durante a Parte 2**
 +    [New 3DS 9.2.0 (Troca de Região) - EUR](https://mega.nz/#!Rg8XlZaR!-q7Xe_GHyt2MEWrLzKc3rxY2fE47QMFk-VN_3PE5i4w) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSDdEY1d1Zkg3eDg/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Troca de Região) - JAP](https://mega.nz/#!x0c3CKBA!zJCScD9i_pVyu3s35N8ap4nLLC6M0GmDyz_VdNunGms) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDTHlWNmlKaFRBM2s/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Troca de Região) - USA](https://mega.nz/#!1oc0XASa!kAeUYyKEKFwdnE31c2hNHjvavSkE5HThDNLpMqXHH4o) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDUURZUmc2d0VSVW8/view?usp=sharing))    
 ~
 +    [3DS Original ou 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [3DS Original ou 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [3DS Original ou 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))    

#### Instruções

1. Extraia o arquivo `GodMode9.bin` do arquivo zip do GodMode9 para a pasta `/luma/payloads` do cartão SD
1. Renomeie o arquivo `GodMode9.bin` na pasta `/luma/payloads` para `up_GodMode9.bin`
2. Copie o arquivo `sysUpdater.cia` do arquivo zip do sysUpdater para a raiz do cartão SD
2. Extraia o arquivo `FBI.cia` do arquivo zip do FBI para a raiz do cartão SD
3. Copie o arquivo `SecureInfo_A` da pasta referente à região para qual você quer mudar do arquivo zip `SecureInfo_A.zip` para a raiz do cartão SD
4. Delete quaisquer pastas `updates` do cartão SD, caso existam
5. Copie a pasta `updates` do arquivo zip do firmware 9.2.0 para a raiz do cartão SD
6. Ejete o cartão SD e insira-o no 3DS
7. Use o FBI para instalar os arquivos `sysUpdater.cia` e `FBI.cia` *(note qual FBI foi instalado via CIA e qual foi injetado no aplicativo Health & Safety)*
8. Retorne ao menu inicial e abra o sysUpdater
9. Pressione Y para realizar o downgrade para a região a qual você deseja trocar
10. Se você receber um erro antes da instalação, segure o botão power para desligar o 3DS e tente novamente (podem ser necessárias várias tentativas)
11. Se o aplicativo travar na mensagem "Rebooting in 10 seconds" por mais de 10 segundos, é seguro desligar o 3DS segurando o botão power
12. Inicie o Decrypt9 por meio do arm9loaderhax segurando, ao ligar o console, o botão Start
13. Selecione a opção "SysNAND Options" e depois "File Dump..."
7. Selecione a opção "Dump SecureInfo_A" e extraia para o arquivo `SecureInfo_A`
17. Pressione Select no menu principal para ejetar o cartão SD
8. Coloque o cartão SD em seu computador e renomeie o arquivo `SecureInfo_A` para `SecureInfo_C` e copie-o para uma pasta segura em seu computador
9. Delete o arquivo `SecureInfo_C` da raiz do cartão SD
10. Abra o arquivo `SecureInfo_C` em seu computador com o editor hexadecimal
11. Vá para o início da linha 00000100 e modifique o primeiro par de números para o par que corresponde à *região que você deseja trocar*:
    - "00" : JPN
    - "01" : USA
    - "02" : EUR
12. Salve o arquivo e copie o arquivo `SecureInfo_C` editado para a raiz do cartão SD
10. Reinsira o cartão SD no 3DS, pressione Start para reiniciar e segure para cima no direcional para inciar o GodMode9    
**(Tenha MUITO cuidado com esta ferramenta, ela pode deixar o aparelho inutilizável caso seja utilizada de maneira errada, mesmo com o arm9loader instalado!)**
11. Navegue até `SDCARD`
12. Pressione Y no arquivo `SecureInfo_C` para copiá-lo
13. Pressione B para retornar ao menu principal
14. Navegue até `SYSNAND CTRNAND` -> `rw` -> `sys`
15. Pressione Y na pasta para colar o arquivo `SecureInfo_C`, sobrescrevendo qualquer arquivo `SecureInfo_C`, caso exista
16. Pressione Start para reiniciar o console
11. Inicie o FBI que foi instalado através do arquivo CIA anteriormente
12. Navegue até o menu "Titles"

Role através dos títulos verdes até que os vermelhos estejam visíveis. Estes são os títulos do sistema instalados na memória interna do console e não no cartão SD. Muito, porém não todos, destes títulos possuirão um código de produto ("Product Code") na tela superior.

**Qualquer título de sistema vermelho que não possuir um código de produto, ou cujo código de produto seja "CTR-P-CTAP" deve ser ignorado para as instruções seguintes!**

    Leia a lista a seguir.
    Determine a letra que corresponde à região ANTERIOR do console.
    Note que deve ser a região de ANTES da mudança de região.

+ "E" : USA
+ "J" : JPN
+ "P" : EUR

Utilize o menu de títulos do FBI para deletar quaisquer títulos cujo código de produto *termine* com a letra da região anterior do console. Isto removerá quaisquer programas de sistema específicos da região anterior que podem causar problemas se mantidos instalados.

**Lembre-se que qualquer título de sistema que não possui um código de produto ou possui o código de produto "CTR-P-CTAP" (mesmo que termine em "P") deve ser ignorado!**

Agora a SysNAND rodando firmware modificado pode ser atualizada para a última versão de sistema.

Se qualquer erro estranho transparecer (especialmente relacionado aos jogos Super Smash Bros. e Monster Hunter 4, caso o console seja um 3DS Original), realize um backup da SysNAND e do cartão SD e formate o console.