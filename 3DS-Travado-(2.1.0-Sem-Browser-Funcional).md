**SE VOCÊ POSSUI UM NEW 3DS E DE ALGUMA MANEIRA FEZ DOWNGRADE PARA O FIRMWARE 2.1 SEM BACKUPS DA NAND OU COM UM BROWSER QUEBRADO, NÃO ATUALIZE. SE VOCÊ ATUALIZAR UM NEW 3DS DA VERSÃO 2.1 PARA UMA VERSÃO POSTERIOR À 6.X O APARELHO FICARÁ INUTILIZÁVEL. NO MOMENTO, VOCÊ DEVERÁ RESTAURAR O SISTEMA A PARTIR DE UM BACKUP DE NAND.**

Se você realizou downgrade para a versão 2.1.0 **em um 3DS Original, 2DS ou New 3DS**, mas por algum motivo o **browser não funciona**, este guia é para você.

Se você realizou downgrade para a versão 2.1.0 **em um 3DS Original ou 2DS**, mas por algum motivo não tem **nenhum backup funcional da NAND** (com o browser funcionando ou não), você pode atualizar utilizando algum [jogo em cartucho](http://www.3dsdb.com/) que contenha um update para a versão 4.X e depois seguir [este guia](https://github.com/Haagenti/Guide-pt_BR/wiki/Atualização-para-a-versão-9.2.0).

Se você realizou downgrade para a versão 2.1.0 **em um New 3DS** mas por algum motivo não tem **nenhum backup funcional da NAND** (com o browser funcionando ou não), até o atual momento o sistema estará inutilizável. Uma solução praticamente funcional está descrita [neste](https://gbatemp.net/threads/424476/) post (link em inglês).

Se você realizou downgrade para a versão 2.1.0 em um **New 3DS** ou **2DS** e **deixou o Wireless desligado** (com o browser funcionando ou não), você pode ligar o wireless novamente removendo a bateria por alguns segundos e depois ligando novamente.

#### Do que você precisa

* Um [jogo em cartucho](http://www.3dsdb.com/) que contenha um update para a versão 4.X
* [Decrypt9WIP 20160118](https://github.com/d0k3/Decrypt9WIP/releases/tag/20160118)
* Um backup válido da NAND.

#### Instruções

1. Copie o arquivo `Launcher.dat` do arquivo zip do Decrypt9WIP para a raiz do cartão SD
2. Copie o backup da NAND para a raiz do cartão SD
3. Inicie o jogo em cartucho que contém o update para a versão **4.X**
4. Aceite o update quando lhe for perguntado
5. Espere até que o console seja reiniciado
6. Abra o browser e vá até `http://www.reboot.ms/3ds/load.html?Launcher.dat`
7. Se a vulnerabilidade foi executada com sucesso, o Decrypt9 será aberto
9. Vá até "SysNAND File Options", depois selecione "NAND Restore"
10. Restaure a NAND a partir do arquivo `sysNAND_original.bin`
