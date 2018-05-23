**Antes de começar a seguir o guia, você deve estar ciente dos riscos de hackear um 3DS. TODA vez que você modifica o console, há a possibilidade de que ele quebre SEM MANEIRA DE CONSERTÁ-LO. Isto é raro, mas é possível que aconteça. Por isso, certifique-se de que você está seguindo TODAS as instruções LETRA POR LETRA.**

Cada parte deste guia foi escrita de maneira a poder ser utilizada de maneira independente a qualquer uma das outras partes. Deste modo, qualquer um pode começar na parte que diz respeito à sua situação. Por isso, certos softwares podem estar listados repetidas vezes na seção "Do que você precisa" do guia. Você não precisa baixá-los novamente.

Este guia está dividido em duas grandes categorias: New 3DS e 3DS Original / 2DS.

O New 3DS é um aparelho mais difícil de realizar os procedimentos, já que ele não foi feito para rodar o firmware 2.1.0. Precisamos dele para realizar o processo de instalação do arm9loaderhax (veja a seção [Informações sobre o OTP](https://github.com/Haagenti/Guide-pt_BR/wiki/Informações-sobre-o-OTP) para informações técnicas sobre o porquê).

O 3DS Original e o 2DS são aparelhos extremamente similares internamente. A única grande diferença no que tange este guia é que, mesmo não existindo instruções para tal, você nunca deve realizar uma formatação de sistema no 2DS enquanto ele estiver em firmwares de versões anteriores à versão 6.0.0. Se o fizer, você não poderá realizar a configuração inicial do sistema e o console ficará preso nela.

Se você precisa formatar um cartão SD novo, você pode usar [esta](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) ferramenta e definir a configuração "Allocation Unit Size" para 32K.

*O seguinte se aplica a todos os consoles:*

**Se você já possui um firmware modificado instalado em qualquer versão entre 9.0.0 e 9.2.0, mude o menuhax para o tipo 1 e defina o botão de inicialização para baixo no direcional. Depois, comece a seguir o guia a partir da [Parte 4 - Obtendo o OTP](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-4-(Obtendo-o-OTP)). Quaisquer menções a "RedNAND" podem ser lidas como "EmuNAND", já que as duas implementações são muito similares e as instruções serão as mesmas.**

Se a versão de firmware for inferior à versão 9.0.0, siga as instruções em [Atualização para a versão 9.2.0](https://github.com/Haagenti/Guide-pt_BR/wiki/Atualização-para-a-versão-9.2.0). 

Se você está nas versões 9.0.0 ou 9.1.0, pode seguir o guia normalmente, já que estas são praticamente idênticas à versão 9.2.0.

Se a versão de firmware estiver entre 9.0.0 e 9.2.0, inicie na [Parte 1 - Homebrew](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-1-(Homebrew)) e depois pule a maior parte da [Parte 2 - Downgrade](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-2-(Downgrade)) (veja mais informações na página).

Se a versão estiver entre 9.3.0 e 10.7.0, inicie na [Parte 1 - Homebrew](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-1-(Homebrew)) e siga todas as instruções.

Se sua versão de sistema é superior à 11.0.0, você deve realizar [downgrade com uma modificação de harware](https://github.com/Haagenti/Guide-pt_BR/wiki/Downgrade-com-Modificação-de-Hardware/)

**Se você seguiu uma versão antiga deste guia que não incluia a SysNAND Atualizada e gostaria de mudar para SysNAND Atualizada + Luma3DS, basta restaurar a SysNAND de um backup de antes da instalação do arm9loaderhax *(como o `sysNAND_original.bin`)* usando o Decrypt9 e siga a [Parte 5 - arm9loaderhax](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-5-(arm9loaderhax)) por completo.**