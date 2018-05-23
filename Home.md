[Clique aqui para ler o guia original em inglês](https://github.com/Plailect/Guide/wiki)

#### Leia todas as páginas introdutórias antes de prosseguir.

**Antes de começar a seguir o guia, você deve estar ciente dos riscos de hackear um 3DS. TODA vez que você modifica o console, há a possibilidade de que ele quebre SEM MANEIRA DE CONSERTÁ-LO. Isto é raro, mas é possível que aconteça. Por isso, certifique-se de que você está seguindo TODAS as instruções LETRA POR LETRA.**

Este guia foi escrito de maneira a levar um 3DS totalmente sem modificações e com firmware de fábrica a um firmware modificado iniciado pelo arm9loaderhax (o que permite o controle quase total do aparelho para instalações de software, etc.).

**Caso você não saiba exatamente qual tipo de 3DS você possui, clique [aqui](https://github.com/Haagenti/Guide-pt_BR/wiki/Informações-sobre-os-Aparelhos) para imagens de cada tipo de console.**

Este guia funcionará no New 3DS, no 3DS original e no 2DS; nas regiões EUR, JAP e USA; e nos firmwares de versão 11.0.0 ou inferior.

Este guia utilizará o arm9loaderhax, o melhor e mais atual método para iniciar firmwares modificados. Ele nos dá controle quase completo do sistema poucos milissegundos após seu início, que é um efeito similar ao do BootMii (método utilizado para hackear o Wii). Os benefícios são muitos, portanto recomenda-se seguir este guia e não qualquer outro que utilize métodos desatualizados (como menuhax ou rxTools). (Utilizaremos o rxTools somente caso você precise atualizar o firmware do console para a versão 9.2.0 pois nada mais suporta versões de firmware tão desatualizadas.)

Você será guiado através dos seguintes passos:  

1. Obtenção de uma entrada para o Homebrew Launcher, para que seja possível a execução de software no console
2. Realização de downgrade para o firmware 9.2.0, de modo a reabilitar as vulnerabilidades do kernel ARM9
3. Downgrade para o firmware 2.1.0, para conseguir o OTP único do console
4. Restauração do firmware 9.2.0
5. Instalação do arm9loaderhax com o firmware modificado Luma3DS para execução de código de maneira permanente na SysNAND


**Se tudo der certo, você não perderá dado algum durante o processo. O console continuará com todos os jogos, o NNID, saves, etc. intactos.**

Os consoles das regiões China (C), Coréia (K) e Taiwan (T) foram lançados após a versão de firmware 4.X, que não permite a extração do OTP. Portanto, sistemas destas regiões *não* poderão realizar o downgrade para obtenção do OTP e instalação do arm9loaderhax.

Uma grande parte deste guia é dedicada a backups de NAND e downgrades, portanto o processo inteiro pode demorar *várias horas* graças ao processador relativamente lento do 3DS.

As regiões C, K e T podem temporariamente ser trocadas por U, E, ou J; mas isto está fora do escopo deste guia.

Este guia foi traduzido por mim, mas originalmente escrito por Plailect. O processo todo foi desenvolvido e refinado pelas pessoas do canal IRC [#Cakey no Freenode](http://webchat.freenode.net/?channels=%23Cakey) (em inglês). Acesse a página de créditos para ver todos os envolvidos, este guia não existiria sem eles.

Valor Sha256 | Arquivo Zip
:---: | :---:
<sub>5736ec8d40303b549f11c06b3811817531e17646a91ee2bb0d94afff69cf3a4e</sub> | <sub>2.1.0E(Full).zip</sub>
<sub>95520c64f3b42a13b8bf266b86edbef9e3ec5e32643ebb6c97f846c2a2647980</sub> | <sub>2.1.0J(Full).zip</sub>
<sub>919e4423a45e019b1984ca7da341ac39282e7992fae62ea37d385b37a8ac621f</sub> | <sub>2.1.0U(Full).zip</sub>
<sub>e7fbaf4ee01b81a3c2297028ef3fddc002f6933bfd20c2453bc6137bda89e5fd</sub> | <sub>9.2.0-20E(Full)_n3DS.zip</sub>
<sub>79407686741732f90db30cd591254f1c591df2dbd9787be78a03b1aceef9f2fe</sub> | <sub>9.2.0-20E(Full).zip</sub>
<sub>9ba7bc4eeab39b484e710d7ad05bfeae3b143812d85bbe128f283a79aa1ba80b</sub> | <sub>9.2.0-20J(Full)_n3DS.zip</sub>
<sub>14c74b462f2db9ba0bdcf1060bfd89345ac9cf863a35092baadd503d6040b837</sub> | <sub>9.2.0-20J(Full).zip</sub>
<sub>38ea53d81763408178d796492d6397cfc1eae422a8a2a4b1270678e1ab30043c</sub> | <sub>9.2.0-20U(Full)_n3DS.zip</sub>
<sub>ff6e7ced330120cdc34cba4536e4ec6609653234d5414f2a727263dfabfe46a3</sub> | <sub>9.2.0-20U(Full).zip</sub>
