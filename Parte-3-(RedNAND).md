Esta parte do guia irá utilizar dois termos que você deve estar familiarizado para entender o que está acontecendo: SysNAND e RedNAND (abreviação para NAND redirecionada). O termo SysNAND refere-se ao chip físico que existe dentro do 3DS que contém todo o software, o sistema operacional, o bootloader e tudo mais (jogos, temas e saves para os jogos instalados são gravados encriptados no cartão SD. Fazer qualquer coisa na SysNAND, mesmo que seja desinstalar um título do sistema, pode resultar em um 3DS inutilizável.

Por causa disso, nós mantemos a SysNAND intacta na versão 9.2.0, mas copiamos-a para uma partição no cartão SD e redirecionamos para ela quando o firmware modificado (CFW) é iniciado. Utilizando este método, você pode isolar as duas NANDs e manter uma cópia 100% vulnerável do sistema na versão 9.2.0 que inicia um sistema operacional secundário na versão mais atualizada, já alterado para permitir que todas as vulnerabilidades funcionem.

Se a SysNAND quebrar por qualquer motivo, você terá um console inutilizável. Porém, se a RedNAND quebrar, é fácil de arrumar. Um erro de SysNAND só pode ser recuperado por meio de soldagem de componentes internos e a escrita de um backup da SysNAND salvo em seu computador para a memória interna do console (ou utilizando o arm9loaderhax, caso este já esteja instalado), mas erros na RedNAND podem ser recuperados bastando apenas um aplicativo como o EmuNAND9 para restaurar a RedNAND a partir de um backup.

Já que a RedNAND funciona de maneira completamente separada da SysNAND, ela pode ser atualizada para a última versão, permitindo assim que todos os jogos funcionem no console hackeado.

**Infelizmente, a RedNAND tem algumas [desvantagens](https://www.reddit.com/r/3dshacks/comments/49qj9w/arm9loaderhax_if_you_dont_like_sysnand_permahax/d0ud80d) (link em inglês), e é por isso que apenas utilizaremos-a para que possamos extrair o OTP antes de instalar o arm9loaderhax e o firmware modificado direto na SysNAND, o que é muito superior.**

Esta parte do guia o ajudará com o processo de instalação da RedNAND e de um firmware modificado no carão SD, e depois com a formatação de uma das NANDs para que as duas sejam isoladas.

Apenas note que os termos EmuNAND e RedNAND referem-se a implementações levemente diferentes do [mesmo conceito](http://3dbrew.org/wiki/NAND_Redirection) (link em inglês).

#### Resumo

Esta seção tem como objetivo ajudá-lo a instalar um CFW (Custom FirmWare/Firmware Modificado), especificamente o Luma3DS (feito pela [AuroraWright](https://github.com/AuroraWright/)), que é capaz de iniciar uma partição RedNAND a partir do cartão SD. Isto requer acesso ao kernel arm9, e é uma das razões pelas quais foi realizado o downgrade para a versão 9.2.0 na parte anterior.

A criação da RedNAND é realizada por um aplicativo chamado EmuNAND9 (criado pelo [d0k3](https://github.com/d0k3/)) que formata o cartão SD para que este possui uma partição que contenha uma cópia da memória interna do console (chip NAND).

Todo o conteúdo pessoal (jogos, saves, dlc, temas, etc.) *não* está na NAND. Apenas os títulos de sistema, alguns arquivos únicos de cada console e um "link" para uma pasta no cartão SD que, por sua vez, *possui* todo o conteúdo. Caso seja executada uma formatação do sistema, o sistema executa troca deste "link", fazendo assim com que o 3DS procure todo o conteúdo em uma nova pasta (que é encriptada com outra chave, para que outras NANDs não possam utilizá-la).

Neste processo, a NAND que contém este link será copiada para a RedNAND. Depois, a SysNAND será formatada para que um processo de "desligamento" ("unlinking") seja realizado. Deste modo, as duas NANDs ficarão completamente separadas, garantindo assim que as duas não usem a mesma pasta do cartão SD (o que pode causar efeitos adversos).

Em seguida, a RedNAND será atualizada para a última versão de firmware mas a SysNAND será mantida desatualizada, pois isto será necessário para a execução da vulnerabilidade do kernel arm9.

#### Do que você precisa

* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* A última versão do [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* A última versão do [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* A última versão do [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* *New 3DS:*
    + O arquivo zip do [firmware bin do NTR para o Luma3DS](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
* *3DS Original:*
    + O arquivo zip do [firmware bin do NTR para o Luma3DS](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instruções

1. Copie o os arquivos `slot0x11key96.bin` e `slot0x25keyX.bin` para a raiz do cartão SD
2. Extraia o arquivo `Luma3DS.dat`, a pasta `3ds` e a pasta `luma` do arquivo zip do Luma3DS para a raiz do cartão SD
3. **Extraia o arquivo `firmware.bin` do arquivo zip do firmware bin do NTR para o Luma3DS para a pasta `/luma/` do cartão SD**
3. Extraia e sobrescreva a pasta `3ds` do arquivo zip do EmuNAND9 para a raiz do cartão SD
4. Extraia a pasta `TinyFormat` do arquivo zip do TinyFormat para a pasta `/3ds/` do cartão SD
5. **Faça backup de todos os arquivos que estiverem no cartão SD para uma pasta em seu computador. Todos os arquivos do cartão serão deletados no próximo passo**
6. Reinsira o cartão SD no 3DS e abra o Homebrew Launcher através da entrada de sua escolha
7. Abra o EmuNAND9 **(várias tentativas podem ser necessárias - se você não conseguir fazer o aplicativo funcionar mesmo depois de tentar muitas vezes, você pode tentar refazer o downgrade para garantir que tudo funcione corretamente)**
8. Selecione a opção "Complete RedNAND setup"
9. Ignore a opção de seleção de `starter.bin` e aperte A para continuar
10. Confirme e aguarde até que tudo seja finalizado
11. Aperte Select no menu principal para ejetar o cartão SD
12. Coloque o cartão SD em seu computador e copie todos os arquivos de volta para ele
13. Reinsira o cartão SD no 3DS e aperte Start para reiniciar
14. Abra o Homebrew Launcher através da entrada da sua escolha
15. Abra o Luma3DS
16. Ative a opção "Show current NAND in System Settings"
17. Aperte Start para iniciar a RedNAND (você deve iniciar o Luma3DS a partir do Homebrew Launcher toda vez que você desejar iniciar a RedNAND)
18. Se o menu inicial for aberto, você iniciou a RedNAND com sucesso
19. Reinicie o sistema para a SysNAND e abra o Homebrew Launcher através da entrada da sua escolha (o menuhax vai sempre iniciar o Homebrew Launcher através da SysNAND)
20. Abra o TinyFormat
21. Aperte Y para formatar a SysNAND (Não se preocupe, tudo ainda estará salvo na RedNAND)
22. Siga com a configuração inicial do sistema sem fazer login com o Nintendo Network ID. Você deverá manter o NNID ligado apenas na RedNAND para evitar quaisquer problemas
23. Reinstale o menuhax na SysNAND
24. Inicie a RedNAND
25. Abra as configurações do sistema
26. **Se não estiver escrito "Emu" na frente da versão de firmware, você não iniciou a RedNAND. NÃO ATUALIZE, DESCUBRA O QUE DEU ERRADO**
27. Atualize a **RedNAND** para a última versão de firmware utilizando as configurações do sistema (**Toda vez que você sai do aplicativo de configurações do sistema ou da seção de gerenciamento de dados do cartão SD, o sistema é reiniciado na SysNAND. Certifique-se de que você iniciou a RedNAND antes de atualizar!**)
28. Até o presente momento, toda vez que desejar iniciar a RedNAND, você deverá abrir o Luma3DS através do Homebrew Launcher. Ao finalizar todos os passos do guia, um firmware modificado será iniciado na SysNAND por padrão