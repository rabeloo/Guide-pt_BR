Todas as variações do sysUpdater, não apenas o PlaiSysUpdater, têm uma chance muito pequena de causar o que chamamos de "soft brick" depois que o downgrade é finalizado e o aparelho reinicia. Isto causará que o aparelho reinicie diretamente à tela de erro da Nintendo que instrui o desligamento do console.

O motivo para tal é desconhecido, mas pode ser previnido executando uma formatação do aparelho antes do processo de downgrade.

Caso o erro aconteça, ele pode apenas ser corrigido entrando no modo de recuperação (A + R + L + Cima no direcional) e atualizando para a última versão de sistema.

Até o momento, a última versão de sistema (11.0.0) bloqueia completamente todas as tentativas de downgrade a partir de software e, se este erro acontecer, não será possível realizar downgrade a menos que seja utilizado uma [modificação de hardware](https://github.com/Haagenti/Guide-pt_BR/Downgrade-com-Modificação-de-Hardware).

*Se você encontrar este erro e não conseguir utilizar o modo de recuperação, você pode editar as configurações de conexão de modo que o aparelho falhe a conectar-se com a Internet.*

Esta versão do PlaiSysUpdater (que é compatível com aparelhos rodando firmwares superiores à versão 9.2.0) utiliza uma vulnerabilidade instável, e por isso podem ser necessárias várias tentativas até que as opções apareçam na tela.

Se o PlaiSysUpdater travar durante qualquer ponto do downgrade (o que pode acontecer ocasionalmente), você pode desligar o console segurando o botão power. Você terá o que é chamado de um "downgrade parcial", "partial downgrade" ou "partial". Porém, é possível consertar isso.

Por mais que um sistema com downgrade parcial possa exibir que está no firmware 9.2.0, você deverá recomeçar o processo do começo para que sejam instalados todos os arquivos que estão faltando. O browserhax continuará funcionando com downgrades parciais contanto que você esteja usando a versão recomendada do PlaiSysUpdater.

**Você DEVE realizar o downgrade com o pacote correto para o console e região. Caso contrário, o aparelho ficará INUTILIZÁVEL.**

**Se o aparelho se encontra na versão 11.0.0, um downgrade por meio de hardware DEVE ser realizado para que esta parte seja concluída com sucesso.**

#### Resumo

O 3DS possui dois processadores incorporados, o arm9 e o arm11. O processador arm11 roda todos os jogos e aplicativos, enquanto o arm9 é responsável pela segurança do sistema em geral, como o gerenciamento de chaves e a verificação de assinaturas.

Para conseguir acesso ao Homebrew Launcher, quebra-se a camada externa do [sistema de segurança do 3DS](https://smealum.github.io/3ds/32c3/#/19) (link em inglês), o espaço de usuário arm11. Isto significa que os privilégios de execução são os mesmos de qualquer outro jogo ou aplicativo. Porém, faz-se necessário ir além.

A vulnerabilidade de kernel arm9 mais recente que funcionava sem passos adicionais ou sem hardware externo foi corrigida com o firmware 9.3.0, ou seja, para conseguir os níveis mais elevados de acesso (que permitem a instalação do arm9loaderhax) é necessário realizar downgrade para uma versão anterior à 9.3.0.

Neste caso, uma vulnerabilidade do kernel arm11 chamada ["svchax"](https://github.com/aliaspider/svchax) (link em inglês) será explorada para que se consiga instalar ou desinstalar os chamados "system titles", que são componentes do sistema operacional do 3DS. Isto permite que o firmware atual seja substituído com um mais antigo, recuperando assim o acesso a vulnerabilidades previamente corrigidas.

Para uma explicação mais detalhada sobre o sistema de segurança do 3DS, leia [este](http://yifan.lu/2016/04/06/the-3ds-cryptosystem/) post no blog do [yifanlu](https://github.com/yifanlu/) (link em inglês).

#### Do que você precisa

* Homebrew Launcher e uma entrada instalada (como o menuhax)
* A última versão do [PlaiSysUpdater](https://github.com/Plailect/PlaiSysUpdater/releases/)
* A última versão do [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* O arquivo zip com o firmware 9.2.0 para o console e região:
 +    [New 3DS 9.2.0 - EUR](https://mega.nz/#!F4U32b4B!tPhl3G0HEmzg5Pd5zQ29ndf1icQqU_LBoogygSL13EY
) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDOWpMTWdybzF3TUU))    
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

**Se a versão do firmware já for a 9.2.0-20, pule para o passo 18.**

1. Extraia e sobrescreva a pasta `3ds` do arquivo zip do PlaiSysUpdater para a raiz do cartão SD
2. Extraia e sobrescreva a pasta `3ds` do arquivo zip do EmuNAND9 para a raiz do cartão SD
3. Delete qualquer pasta chamada `updates` do cartão SD, caso exista alguma
4. Extraia a pasta `updates` do arquivo zip do firmware 9.2.0 para a raiz do cartão SD
5. Remova o cartão SD de seu computador e coloque-o no 3DS
6. Acesse o Homebrew Launcher (se você seguiu a parte anterior, você pode fazer isso ligando o 3DS enquanto segura para baixo no direcional)
**Se a entrada sendo utilizada for o supermysterychunkhax ou o smashbroshax, qualquer aplicativo homebrew (como o menuhax_manager) deve ser aberto e em seguida fechado para que se retorne para o Homebrew Launcher (o que consertará o conteúdo da memória do console). Se isto não for feito, o svchax não iniciará corretamente.**
7. Abra o PlaiSysUpdater
8. Se as opções não aparecerem na tela, segure o botão power para desligar o 3DS e tente novamente (várias tentativas podem ser necessárias)
9. Se as opções aparecerem, siga em frente
10. Aperte Y para realizar o downgrade para a versão 9.2.0
11. Espere. Não aperte nenhum botão e não mexa em nada, mesmo que pareça que o aplicativo travou
12. Se depois de 30 segundos ainda parece que o aplicativo está travado, é seguro desligar o console segurando o botão power e tentar novamente
13. Se você receber um erro antes da instalação começar, segure o botão power para desligar o 3DS  e tente novamente (várias tentativas podem ser necessárias)
14. Se você receber um erro no meio da instalação, siga as instruções no início deste parte para downgrades parciais
15. Se o aplicativo travar na mensagem "Rebooting in 10 seconds" por mais de 10 segundos, é seguro desligar o 3DS segurando o botão power
16. Se você receber uma tela preta depois de realizar o downgrade, [siga este guia para resolução de problemas](https://github.com/Haagenti/wiki/Resolução-de-Problemas#ts_sys_down)
17. Quando o sistema reiniciar ou você ligá-lo novamente, mude o tema para qualquer outro e depois retorne para o antigo, para que assim a versão antiga do menuhax seja removida
18. Reinstale o menuhax utilizando o browserhax e o Homebrew Launcher (você não precisa reconfigurar nada, apenas aperte "install" depois de abrir o menuhax_manager)
19. Abra as configurações do sistema, a versão deverá ser a 9.2.0
20. Abra o Homebrew Launcher usando a entrada de sua escolha (como o menuhax)
21. Abra o EmuNAND9 **(várias tentativas podem ser necessárias)**
22. Vá para "EmuNAND Manager Options" e faça um backup da SysNAND para `sysNAND.bin`
23. Aperte Select no menu principal para ejetar o cartão SD
24. Coloque o cartão SD em seu computador e depois copie o arquivo `sysNAND.bin` para algum lugar seguro. É recomendado que você guarde bem este backup, já que ele que o salvará no futuro caso qualquer coisa dê errado. **(O tamanho do backup deverá ser igual a um dos tamanhos citados [nesta](https://github.com/Haagenti/Guide-pt_BR/wiki/Tamanhos-de-NAND) página. Caso contrário, você deverá deletá-lo e realizar um novo backup!)**
25. Você pode deletar o arquivo `sysNAND.bin` do cartão SD após copiá-lo
26. Coloque o cartão SD novamente no 3DS e depois aperte Start para reiniciar