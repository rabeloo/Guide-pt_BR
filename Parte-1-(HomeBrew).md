O Homebrew Launcher possui várias portas de entrada (maneiras de iniciá-lo). A maneira mais comum é o browserhax, que inicia o Homebrew Launcher usando nada além do browser do próprio 3DS. Depois, pode-se instalar o menuhax, que permite que você segure um botão enquanto o console liga para iniciar o Homebrew Launcher antes que o resto do sistema inicie.

Se o console está entre as versões 9.0.0 e 9.8.0, você pode seguir este guia, mas você não precisa realizar o passo de mudança de data e hora.

Se o console está entre as versões 9.9.0 e 10.5.0, você deve seguir o guia passo por passo.

Se o console está entre as versões 10.6.0 e 11.0.0 ou o browser do aparelho possuir uma versão (os últimos dois dígitos do número da versão de firmware, por exemplo: 11.0.0**-33**) inferior à versão **-20**, você deve seguir as instruções para as várias entradas alternativas abaixo *em vez de seguir esta página*: 
+ [Ninjhax](http://smealum.github.io/ninjhax2/) (link em inglês), que necessita do jogo Cubic Ninja **(temporariamente não-funcional com o FIRM 11.0.0, um update está a caminho; não se aplica a usuários de modificações via hardware)**
+ [smashbroshax](https://gbatemp.net/threads/397194/) (link em inglês) (requer Super Smash Bros. e **funciona apenas no New 3DS**) 
+ [oot3dhax](https://github.com/yellows8/oot3dhax) (link em inglês), que necessita do jogo Ocarina of Time 3D e o Powersaves para editar os saves de jogos em cartucho ou acesso a outro 3DS que já possui o Homebrew Launcher **(temporariamente não-funcional com o FIRM 11.0.0, um update está a caminho; não se aplica a usuários de modificações via hardware)**
+ [supermysterychunkhax](https://smd.salthax.org/) (link em inglês), que necessita do jogo Pokémon Super Mystery Dungeon e acesso a outro 3DS que já possui o Homebrew Launcher  

**Se o console está na versão 11.0.0, um downgrade por meio de hardware DEVE ser utilizado para que a Parte 2 seja realizada com sucesso posteriormente.** 

As vulnerabilidades que habilitavam o browserhax e o menuhax foram corrigidas no firmware 10.6.0 e não funcionarão em sistemas com firmwares posteriores.

Se a versão de firmware for inferior à 9.0.0, você pode seguir as instruções para atualizar o sistema para a versão 9.2.0-20 [aqui](https://github.com/Haagenti/Guide-pt_BR/wiki/Atualização-para-a-versão-9.2.0). O browserhax não é suportado em versões inferiores à 9.0.0.

Se o console está nas versões 10.6.0/10.7.0 e você estiver utilizando um jogo para acessar os hacks, sempre inicie o Homebrew Launcher por meio do jogo em vez do menuhax. Após realizar o downgrade para a versão 9.2.0, o jogo não será mais necessário para seguir o resto deste guia.

#### Resumo

Esta seção tem como objetivo ajudá-lo a baixar o Kit Inicial para Homebrew do [smea](https://github.com/smealum), que inclui o arquivo necessário para executar o Homebrew Launcher (`boot.3dsx`) e outros aplicativos úteis (os apps da pasta `/3ds/`).

Todas as entradas do tipo \*hax (que são as entradas mais comuns, como por exemplo: Ninjhax, oot3dhax, menuhax e browserhax), depois de instalarem seu código, iniciam um arquivo chamado `boot.3dsx` que, no nosso caso, é o Homebrew Launcher. O arquivo em si pode ser qualquer aplicativo homebrew no formato `.3dsx`, mas o Homebrew launcher é o melhor aplicativo para isso, já que ele permite que *outros* programas homebrew sejam executados.

Este guia utilizará o browserhax, que executa o Homebrew Launcher através de uma vulnerabilidade localizada em um site, para instalar o menuhax (um tema do 3DS que permite a execução do Homebrew Launcher logo ao iniciar o console). Ambas entradas foram corrigidas no firmware 10.6.0 e, por isso, se o console utilizado estiver rodando uma versão de sistema posterior a esta, uma das entradas alternativas citadas no topo se fará necessária.

Todas as versões de firmware posteriores a 9.9.0 incluem uma checagem de browser que não permite que qualquer site sejea visitado se a última versão não estiver instalada. Isto normalmente significaria que, se a última versão de sistema não estiver instalada, seria necessário executar uma atualização para visitar o site do browserhax, mas esta atualização corrigiria a vulnerabilidade explorada pelo próprio browserhax.

A [alternativa](https://yls8.mtheall.com/3dsbrowserhax.php) encontrada, descoberta pelo [yellows8](https://github.com/yellows8), é mudar o relógio do sistema para a data descrita abaixo e inicializar o arquivo de save do browser rapidamente (*antes* que o 3DS conecte-se com a Nintendo para verificar a versão do browser). Depois disso, o browser poderá ser utilizado normalmente até que se saia do mesmo ou o relógio atinja um dia depois da data citada.

Depois disso, o menuhax será instalado para que se inicie o arquivo `boot.3dsx` (no nosso caso, o Homebrew Launcher) quando o direcional for segurado para baixo ao se iniciar o console.

#### Do que você precisa

+ Do [Kit Inicial](http://smealum.github.io/ninjhax2/starter.zip) para Homebrew
+ Uma conexão de Internet funcional e já configurada no 3DS

#### Instruções

1. Extraia o conteúdo da pasta `starter` contida no arquivo `starter.zip` para a raiz do cartão SD e coloque-o no 3DS
2. Abra o menu de temas do 3DS, mude o tema para qualquer outro, depois volte ao original. Isso inicializará os dados de tema
3. Abra as configurações do console
4. Mude a data para `1 de Janeiro de 2000`
5. Mude a hora para `00:00`
6. Abra o browser e depois abra as configurações do browser o mais rápido que puder
7. Role a tela até o final e clique em Initialize Savedata (o botão também pode se chamar Clear All Save Data) o mais rápido que puder
8. Navegue até `http://yls8.mtheall.com/3dsbrowserhax_auto.php` no 3DS ou escaneie o QR Code abaixo (se for exibido um botão deslizante, faça zoom máximo nele e clique na ponta direita do mesmo; isso pode precisar de algumas tentativas)
![browserhax_auto](https://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
9. O console deverá carregar o Homebrew Browser
10. Abra o aplicativo menuhax_manager
11. Aperte A para instalar. Ele poderá exibir alguns erros, mas está tudo certo desde que a mensagem "Success" apareça no final
12. Volte para o menu principal do menuhax_manager, e então selecione "Configure/check haxx trigger..."
13. Aperte A para continuar, e então selecione "Type1"
14. Segure para baixo no direcional e então clique na tela de toque; este é o botão recomendado para iniciar o menuhax neste guia porque ele não interfere com nenhuma outra função das ferramentas que utilizaremos
15. Retorne para o menu principal do menuhax_manager e aperte B depois Start para retornar ao Homebrew Launcher
16. Aperte Start para reiniciar o sistema
17. Agora você pode segurar para baixo no direcional enquanto o console liga para iniciar o Homebrew Launcher
