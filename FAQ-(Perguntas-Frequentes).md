+ <a name="faq_latestfw" />**P:** *Estou na última versão de firmware. Posso hackear meu 3DS?*    
  **R:** A versão 11.0.0 só pode ser hackeada através de uma [modificação de hardware](https://github.com/Haagenti/Guide-pt_BR/wiki/Downgrade-com-Modificação-de-Hardware) que requer a solda de um acesso direto à NAND.

+ <a name="faq_n3ds" />**P:** *Preciso fazer algo diferente em um New 3DS do que eu faria em um 3DS Original/2DS?*    
  **R:** Com a exceção de algumas versões de arquivos diferentes, o processo é o mesmo para todos os modelos de aparelho, já que o OTPHelper detecta automaticamente qual modelo está sendo utilizado e executa a ação necessária ao selecionar a opção "One Click Setup".

+ <a name="faq_updatecfw" />**P:** *Como eu atualizo o Luma3DS?*    
  **R:** Use o Luma3DS Updater.

+ <a name="faq_rednand" />**P:** *Qual a diferença entre RedNAND e EmuNAND?*    
  **R:** RedNAND e EmuNAND são dois tipos diferentes de [redirecionamento de NAND](http://3dbrew.org/wiki/NAND_Redirection) (link em inglês) com pequenas diferenças na maneira em que funcionam por trás dos panos. A mais vantagem de usar RedNAND em vez de EmunNAND é que RedNAND *sempre* utilizará o menor [tamanho de NAND](https://github.com/Haagenti/Guide-pt_BR/wiki/Tamanhos-de-NAND) que o aparelho oferece, infepente do tamanho do chip da SysNAND. Por exemplo, para um New 3DS com um chip NAND interno de 1.8GB, só serão utilizados 1.2GB para todos os backups da RedNAND.

+ <a name="faq_gatewaysky" />**P:** *Ouvi falar de algo que eu preciso comprar para hackear meu 3DS (Gateway, Sky3DS, etc), eu preciso disso?*    
  **R:** Não. O arm9loaderhax é um metodo melhor de inciar hacks que roda logo ao ligar o sistema e permite a instalação de coisas como firmwares modificados e mais.

+ <a name="faq_need" />**P:** *Do que eu preciso para seguir este guia?*    
  **R:** Este guia pode ser seguido até o final apenas com software gratuito e, **caso o console esteja rodando firmware de versão 10.6.0 ou 10.7.0)**, um jogo compatível.    
    *Nota: Se você está utilizando um jogo para ter acesso aos hacks, você deverá entrar no Homebrew Launcher utilizando-o em vez do browserhax ou do menuhax. Após completar o downgrade inicial para o firmware 9.2.0, você não precisará mais do jogo para seguir o resto do guia.*

+ <a name="faq_risky" />**P:** *Quão arriscado é o processo de hackear meu console?*    
  **R:** Bricks (consoles inutilizados) são *basicamente* impossíveis a não ser que você ignore todas as checagens de segurança.

+ <a name="faq_piracy" />**P:** *Ao fim do guia, poderei instalar jogos piratas?*    
  **R:** [Yes](https://github.com/HouseBreaker/Shameless/). Não me faça quaisquer outras perguntas relacionadas a pirataria pois as mesmas não serão respondidas.

+ <a name="faq_piracy_online" />**P:** *Posso jogar online com jogos piratas sem ser banido?*    
  **R:** Se você instalou o jogo por meio de um arquivo CIA, você não será banido. Se você está usando um flashcart (como o Sky3DS), você poderá ser banido.

+ <a name="faq_piracy_header" />**P:** *Precisarei de private headers (cabeçalhos privados)?*    
  **R:** Eles são necessários somente para flashcarts. Se você instalou o jogo por meio de um arquivo CIA, você não precisa deles.

+ <a name="faq_homebrew" />**P:** *Posso rodar aplicativos e emuladores ao fim do guia?*    
  **R:** Sim! Firmwares modificados não apenas permitem o uso do Homebrew Launcher como também lhe permitem acesso a hacks em todas as versões, o que significa que você pode ter o console hackeado para sempre, mesmo após updates.

+ <a name="faq_regionfree" />**P:** *Ao fim do guia, poderei rodar jogos de outras versões?*    
  **R:** O Luma3DS suporta patches Region Free, que permitem a instalação de jogos de qualquer região sem quaisquer outras modificações ou passos.

+ <a name="faq_updates" />**P:** *É seguro atualizar meu console após a instalação de um CFW (firmware modificado) na minha SysNAND?*    
  **R:** Sim, mas se você se sentir apreensivo(a), você pode esperar pela confirmação da comunidade de que tudo está funcionando.

+ <a name="faq_support" />**P:** *Para onde devo ir para suporte?*    
  **R:** Para suporte em português, contate-me em haagenti@tuta.io. Para suporte em inglês, contate qualquer operador do canal [#3dshacks no IRC Rizon](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

+ <a name="faq_le4gbsd" />**P:** *Posso seguir um guia com um cartão SD de 4GB (ou inferior)?*    
  **R:** Você pode conseguir concluir o guia com um cartão de 4GB, mas com cartões menores será difícil. A própria RedNAND toma cerca de 1GB do espaço do cartão e os backups da NAND também são grandes. Você pode ter de desconectar o cartão SD do 3DS para transferir arquivos de/para seu computador com mais frequência do que o guia orienta. Faça-o por conta e risco.

+ <a name="faq_ge128gbsd" />**P:** *Posso usar um cartão SD de 128GB (ou superior)?*    
  **R:** Sim, mas alguns usuários reportaram lentidão ao usar cartões de tamanhos tão grandes. Fique ciente de que você não poderá formatar o cartão em exFAT, você terá de formatá-lo usando FAT32.

+ <a name="faq_movesd" />**P:** *Como faço caso eu queira trocar de cartão SD após terminar de seguir o guia?*    
  **R:** Basta copiar todos os arquivos do cartão SD antigo para o novo.

+ <a name="faq_NNID" />**P:** *O que acontece com o meu NNID?*    
  **R:** Se você começou o guia com um NNID associado ao console e seguiu todos os passos corretamente, você continuará com o mesmo NNID ao final.

+ <a name="faq_systransfer" />**P:** *E a função "System Transfer" (Transferência de sistema)?*    
  **R:** Após completar o guia, você poderá realizar transferências de sistemas de/para um sistema hackeado exatamente da mesma maneira que você faria para um console normal ou com EmuNAND, com a exceção de que você perderá todo o conteúdo (jogos/temas/DLC) não original durante a transferência. Jogos salvos serão transferidos mesmo para os jogos que foram perdidos no processo.

+ <a name="faq_nopc" />**P:** *Posso seguir o guia sem ter um computador (ex. com um celular Android)?*    
  **R:** Você pode conseguir completar até a Parte 3 do guia (RedNAND). De todo modo, a Parte 4 necessita de um computador para injetar o FBI no aplicativo Health & Safety.

+ <a name="faq_problem" />**P:** *Socorro! Algo horrível aconteceu e agora meu console não liga!*    
  **R:** Cheque a seção [[Resolução de Problemas|Resolução-de-Problemas]].
