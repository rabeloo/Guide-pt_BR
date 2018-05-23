Grande parte dos aplicativos e firmwares modificados foram feitos para serem utilizados com a SysNAND entre as versões 9.0.0 e 9.2.0. Se você está em uma versão inferior à 9.0.0, você precisará utilizar este guia para atualizar o console sem fazer com que ele fique na última versão.    

Se você está entre as versões 9.0.0 e 10.7.0 você pode seguir as instruções descritas [aqui](https://github.com/Haagenti/wiki/Iniciando-o-Processo).

Se você já possui a RedNAND instalada, este guia lida apenas com a SysNAND e você deve seguir todas as instruções a partir da SysNAND.

Os termos EmuNAND e RedNAND referem-se a implementações levemente diferentes do [mesmo conceito](http://3dbrew.org/wiki/NAND_Redirection) (link em inglês).

**Esta seção do guia provavelmente não funcionará em sistemas inferiores à versão 4.0.0. Atualize o sistema para uma versão entre 4.0.0 e 9.2.0 a partir de um jogo em cartucho que [contenha a atualização](http://www.3dsdb.com/) desejada.**

#### Do que você precisa

* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* [rxTools 2.5.2](https://github.com/roxas75/rxTools/releases/download/2.5.2/release.rar) ([Mirror](http://rxtools.net/php/downloads.php?dl=rxTools%20v2.5.2))
* [Decrypt9WIP 20160118](https://github.com/d0k3/Decrypt9WIP/releases/tag/20160118)
* A última versão do [sysUpdater](https://github.com/profi200/sysUpdater/releases/)
* A última versão do [FBI](https://github.com/Steveice10/FBI/releases/)
* A última versão do [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* O arquivo zip do firmware 9.2.0 referente ao tipo de aparelho e região:
 +    [New 3DS 9.2.0 - EUR](https://mega.nz/#!F4U32b4B!tPhl3G0HEmzg5Pd5zQ29ndf1icQqU_LBoogygSL13EY) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDOWpMTWdybzF3TUU))    
 +    [New 3DS 9.2.0 - JAP](https://mega.nz/#!VxcF3TIK!Bm5LgFxo5V4Nepe9ZlWnx7bichE1V7p7pR_HqwimU5M
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDU2plUWwxa2gtV0E/view?usp=sharing))    
 +    [New 3DS 9.2.0 - USA](https://mega.nz/#!gslWiIoK!SF7uFk9rzWTK6oitCDoeAdvphcCzhKWsnTAMXw7zwOU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDbEV2aTRjb1oxekE/view?usp=sharing))    
 ~
 +    [3DS Original ou 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [3DS Original ou 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [3DS Original ou 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))    

#### Instruções

1. Copie o arquivo `slot0x25keyX.bin` para a raiz do cartão SD
2. Extraia o arquivo `rxTools.dat` do arquivo zip do rxTools  para a raiz do cartão SD
3. Extraia o arquivo `Launcher.dat` do arquivo zip do Decrypt9WIP para a raiz do cartão SD
4. Delete quaisquer pastas `updates` do cartão SD, caso existam
5. Extraia a pasta `updates` do arquivo zip do firmware 9.2.0 firmware para a raiz do cartão SD
6. Extraia o arquivo `sysUpdater.cia` from the sysUpdater zip para a raiz do cartão SD
7. Ejete o SD card e coloque-o de volta no 3DS
8. Abra o browser do 3DS e vá para `http://www.reboot.ms/3ds/load.html?Launcher.dat`
9. Se a vulnerabilidade foi executada com sucesso, o Decrypt9 será iniciado
10. Acesse a opção `SysNAND File Options`, depois selecione `Dump Health & Safety` para extrair o aplicativo Health & Safety para o arquivo `hs.app`
11. Pressione Select para ejetar o cartão SD e depois insira-o em seu computador
12. Extraia o Universal Inject Generator e copie os arquivos `hs.app` do cartão SD e `FBI.cia` arquivo zip do FBI para a pasta `input`
13. Clique duas vezes no arquivo `go.bat`
14. Copie o arquivo `FBI_inject_with_banner.app` para a raiz do cartão SD e reinsira o cartão SD no 3DS
15. Pressione B no Decrypt9, selecione a opção `SysNAND File Options` e depois `Inject Health & Safety`
16. Pressione Baixo uma vez para selecionar o arquivo `FBI_inject_with_banner.app` e pressione A para injetar
17. Volte às opções de RedNAND no Decrypt9 *(Se uma RedNAND estiver instalada)*
18. Realize backup da RedNAND para o arquivo `emuNAND.bin` *(Se uma RedNAND estiver instalada)*
19. Retorne às opções de SysNAND no menu principal
20. Realize backup da SysNAND para o arquivo `sysNAND.bin`
21. Pressione Select no menu principal para ejetar o cartão SD
22. Insira o cartão SD em seu computador e renomeie os arquivos `sysNAND.bin` e `emuNAND.bin` *(se existir um)* para `sysNAND-OLD.bin` e `emuNAND-OLD.bin`
23. Copie os arquivos `sysNAND-OLD.bin` e `emuNAND-OLD.bin` *(se existir um)* para uma pasta segura em seu computador para caso você queira restaurar o sistema para esta versão algum dia
24. Delete os arquivos `sysNAND-OLD.bin` e `emuNAND-OLD.bin` *(se existir um)* do cartão SD
25. Reinsira o cartão SD no 3DS e pressione Start to reiniciar o aparelho
26. Abra o browser do 3DS e vá até `http://www.reboot.ms/3ds/load.html?rxTools.dat`
27. Se a vulnerabilidade foi executada com sucesso, o rxTools foi iniciado e será pedido que o botão R seja pressionado. Faça isso
28. Espere enquanto os arquivos são instalados
29. Selecione a opção `Devmode`
30. O 3DS será reiniciado ao menu inicial
31. Abra o aplicativo Health and Safety (que agora é o FBI)
32. Navegue até o arquivo `sysUpdater.cia` e pressione A para instalar
33. Se uma mensagem parecida com "database error" aparecer, isso acontece porque a eShop nunca foi acessada neste aparelho. Para consertar isto, insira o cartão SD em seu computador e abra a pasta `Nintendo 3DS`. Agora você deverá entrar nas duas primeiras pastas. Os nomes das pastas serão números e letras aleatórios. Agora entre na pasta `dbs` e crie dois arquivos vazios chamados `title.db` e `import.db` em cada uma destas pastas. Insira o cartão SD de volta no 3DS, abra as configurações, vá em 3DS > Software. O sistema dirá que o banco de dados deverá ser reconstruído. Aguarde e depois refaça os passos 9 até 17.
34. Aperte o botão Home para retornar ao menu inicial, abra o aplicativo sysUpdater e pressione o botão A para instalar

Agora você pode seguir o guia a partir [daqui](https://github.com/Plailect/Guide/wiki/Iniciando-o-Processo).
