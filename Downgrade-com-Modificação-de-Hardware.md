**A versão do autofirm utilizada neste guia foi modificada a partir da original criada pelo [Raugo](https://gbatemp.net/members/356694/) do [Reboot.ms](https://www.reboot.ms/forum/threads/2403/). Foi criado um link mirror para as pessoas que não falam italiano com a devida [autorização](https://www.reddit.com/r/3dshacks/comments/4ipeuh/guide_downgrade_from_110_to_92_via_hardmod/d30ipdf?context=1).**
 
Se o console utilizado estiver na versão 11.0.0, faz-se necessário seguir este guia para realizar downgrade do NATIVE_FIRM utilizando uma modificação de hardware, que nos permite a extração e restauração direta da NAND.    
 
Se o console utilizado estiver em uma versão de sistema inferior à 9.0.0 então você deve seguir [este](https://github.com/Haagenti/Guide-pt_BR/wiki/Atualização-para-a-versão-9.2.0) guia para realizar a atualização.    

Se o console utilizado estiver entre as versões 9.0.0 e 10.7.0 você pode simplesmente seguir as instruções listadas [aqui](https://github.com/Haagenti/Guide-pt_BR/wiki/Iniciando-o-Processo).    

**Um guia excelente, porém em inglês, para a instalação da modificação de hardware pode ser encontrado [aqui](https://gbatemp.net/threads/414498/).**

Existe uma implementação funcional da vulnerabilidade "FIRM partitions known-plaintext" detalhada [aqui](https://www.3dbrew.org/wiki/3DS_System_Flaws) (link em inglês).

Este guia funcionará em todas as versões do 3DS (3DS Original e New 3DS).

**Após seguir estas instruções na versão 11.0.0 você deve possuir uma entrada alternativa (como as listadas na página [Iniciando o Processo](https://github.com/Haagenti/Guide-pt_BR/wiki/Iniciando-o-Processo)) para conseguir iniciar o Homebrew Launcher e realizar o downgrade.**

#### Do que você precisa

* Um backup da NAND do console na versão 11.0.0 extraída utilizando a [modificação de hardware](https://gbatemp.net/threads/414498/) (link em inglês)
* [Autofirm 11.0 - Reboot edition](https://mega.nz/#!dl8ASTjB!2jsKbAYTAlspHhxYCt9Wzvia74xEvgtzGQxGLe3TJiM) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRTlwYUQ1NDJoVlk))
* Os CIAs do NATIVE_FIRM desencriptado versões 10.4.0 e 11.0.0 para o aparelho sendo utilizado:
    + [3DS Original 10.4.0 - 0004013800000002 v23341](https://mega.nz/#!I5EmyCZC!pU-bG9Esg30LINlasTP43Sei6aDNnTIzh1ojwECKOrU) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUGxYbmkwVThSUHc))    
    + [3DS Original 11.0.0 - 0004013800000002 v24368](https://mega.nz/#!AgUGAbKD!0iNXI1ioLM7mBzACfBrPLotYk8g-LzcdTgcuTsQCmHQ) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaG1jbERyQ1BGcHc))    
    + [New 3DS 10.4.0 - 0004013820000002 v23341](https://mega.nz/#!1xcEAApQ!anu5UenuD-uEm6z14n680rQThEgViAsytWh5ZuTa_hc) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRHlOTWJZNGtxVkk))
    + [New 3DS 11.0.0 - 0004013820000002 v24368](https://mega.nz/#!dk8BgZaJ!8EM0Wk4NHl6-_O4hhcatIpAx-vfkjMKZs7uQh__OKRw) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeVhnUU1semtNQjQ))

#### Instruções

1. Extraia os conteúdos do arquivo `autofirm_Reboot_11.0.zip` para uma pasta chamada `autofirm_Reboot_11.0`
2. Coloque uma cópia do backup da NAND (nomeado `nand.bin`) na pasta `autofirm_Reboot_11.0`
4. Coloque os dois arquivos CIA do NATIVE_FIRM que correspondem ao aparelho sendo utilizado na pasta `autofirm_Reboot_11.0`
7. Rode o arquivo `autofirm_ENG.bat` e selecione de qual aparelho o backup da NAND foi gerado
8. Espere enquanto o script roda
8. Se tudo funcionou corretamente, será obtido um arquivo `nand.bin` modificado contendo o NATIVE_FIRM 10.4.0 na versão de sistema 11.0.0
9. Restaure o arquivo `nand.bin` para o aparelho através da modificação de hardware

O número da versão exibido *não* terá mudado nas configurações do sistema, mas o processo foi executado com sucesso.

Você poderá, a partir de agora, seguir o resto deste guia a partir [desta página](https://github.com/Haagenti/Guide-pt_BR/wiki/Parte-1-(Homebrew)). Lembre-se de que ainda há a necessidade de uma entrada alternativa para o Homebrew Launcher.