This is a fork of the [Dactyl-Manuform](https://github.com/abstracthat/dactyl-manuform).
Check the original [README](https://github.com/dezzare/dactyl-manuform/README.original.md)


# O Teclado Dactyl-ManuForm
Primeiramente, devo destacar que não sabia soldar antes de começar este projeto. Então, se eu consegui você também consegue.
O resultado final da minha implementação:
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img15.jpeg)

O resultado com os keycaps do teclado doador:
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img11.jpeg)

Eu construi uma versão 5x6, os modelos para impressão você pode encontrar em:

* [Parte Esquerda](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/left-5x6.stl)
* [Parte Direita](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/right-5x6.stl)
* [Tampa Esqueda](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/Left_5x6_Bottom_Plate.stl) 
* [Tampa Direita](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/Right_5x6_Bottom_Plate.stl)

Há diversas outras opções de tamanho, você pode checar o readme ou o repoositório original.

## Montagem

### Material

Aqui está o material que você vai precisar para a montagem, na forma que eu fiz.

* Dois Arduino Pro Micros (Artmega32u4)
* Switches (Keyboard Switches)
* Keycaps
* Parafuso M3 + "bucha"
* Fios Jumper Femea
* Diodos 1N4148
* Conector RJ-9 Femea
* Cabo RJ-9
* Adaptador Micro USB Macho p/ USB Femea
* Interruptor p/ reset

Além disto, ainda é necessário ter ferro de solda, estanho, alicate, multímetro e demais ferramentas que você acha que facilitaria sua vida para montar.

Algumas observações em relação ao material:

#### Switches e Keycaps 
Compre os Keycaps.
No meu projeto eu utilizei um teclado antigo, já com defeito, para não ter que comprar Switches e Keycaps. Porém os keycaps tem tamanho diferentes de altura, o que tem me incomodado.  

#### Parafuso M3 e "Bucha"
Eu moro em uma cidade pequena, tive dificuldade de achar a "bucha" para o parafuso. 
Então eu peguei o que encontrei e cortei na metade: 

![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img10.jpeg)

A metade de cima não tinha "ranhura", por isso utilizei a outra metade. Não é o ideal, mas serviu. 

#### Fios Jumper Fêmea 
Em tese eles não são essenciais para a construção do teclado, você pode solda a fiação direto na placa arduíno. Porém, aconselho MUITO você soldar os ferrinhos que vem junto (foto) e conectar os jumper neles, assim facilita na organização e eventual manutencão, 
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img12.jpeg)


#### Conector RJ-9 Fêmea e Cabo RJ-9
Aqui tem um pulo do gato. Aconselho altamente este conector.
Este conector vai servir para interligar as duas metades do teclado. Então o conector precisa, no mínimo, 3 vias(dados, positivo, "terra").
Você pode substuir este conector por um conector P2 TRS, ou TRRS. PORÉM, toda vez que você conectar/desconectar, um teclado no outro, estará causando um curto. Então, TODA vez que conectar/desconectar uma parte na outra, eles NÃO PODEM estar conectados no computador(energizados). Por isso aconselho o rj-9.

ATENÇÃO 1: ele não é um conector igual telefone, ele tem 4 vias (telefone tem 2 normalmente), certifique-se de estar pegando o de 4 vias. 
ATENÇÃO 2: o mesmo vale para o CABO, certifique-se que ele tem 4 vias. Se quiser você pode montar o seu. 
ATENÇÃO 3: os cabos montados tem suas pontas espelhadas, ou seja, o fio do lado esquerdo será o do lado direito na outra ponta (em um dos lados vc conectará fios diferentes no arduino. Falarei mais a respeito no momento da montagem)
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img13.jpeg)
  

#### Adaptador Micro USB Macho p/ USB Femea
Aqui vai muito de preferência de cada um, vi diversas montagens com adaptação para USB C, porém não encontrei para venda. 
Optei por esta solução por ser a mais na mão, e deu super certo. 
Só tive que descascar o cabo e ele coube perfeitamente no local reservado pra ele na impressão. 
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img9.jpeg)


#### Interruptor p/ reset
Este é outro pulo do gato. Ele não é extremamente necessário, mas nem vou entrar em detalhes, simplesmente compre e utilize na montagem. 
Este foi o que eu usei, e sofri bastante para soldar. Há opções melhores, com as "perninhas" maiores (será mais fácil para você soldar)
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img14.jpeg)



### Juntando tudo 

A primeira coisa a ser feita é colocar os Switches no lugar:
![Img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img1.jpeg)

Para montagem eu utilizei o seguinte diagrama para solda e conexão no arduino
![Left Wire Diagram](/resources/dactyl_manuform_left_wire_diagram.png)

![Right Wire Diagram](/resources/dactyl_manuform_right_wire_diagram.png)

Solde primeiramente as colunas, eu usei fios elétricos normais e conectei as pontas com o fio jumper.
Na minha opinião, acho melhor soldar as colunas e o fio jumper antes de começar a solda as linhas com os diodos.

![img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img4.jpeg)
![img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img6.jpeg)

Após soldado as colunas, faça as linhas soldando os diodos.
ATENÇÃO: o lado dos diodos importam, fique atento, coloque o risco preto para fora conectando com os outros diodos. 

![img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img5.jpeg)


Caso você tenha optado pelo conector RJ-9, agora é a hora de conectar ele. 
No meu caso eu tive que gastar um pouco a lateral do conector para caber no local destinado p/ ele.
Lembre que caso você tenha comprado um cabo pronto, você deve se atentar que a solda/conexão no segundo arduino muda conforme a sua escolha dos fios a conectar no primeiro.
Como assim a ordem muda? Simples, eles são espelhado. Em um lado você terá a ordem 1-2-3-4 e na outra ponta ele será 4-3-2-1. Então se você escolheu o fio 1 p/ ser o de dados, tenha certeza que pegue o fio 4 na outra ponta para conectar no local destinado a dados.
Você também pode optar em fazer o seu próprio cabo, ai você não terá esse problema.

Conecte o adaptador USB.
![img](https://github.com/dezzare/dactyl-manuform/blob/master/dezzare/img/img8.jpeg)

Escolha o local onde você colocará o botão reset. Faça um furo, mas antes de coloca-lo lá e prender com cola-quente solde os fios nas pontas dele. Conecte o botão na placa.
Pronto, teclado finalizado. Agora é só configurar do seu jeito.


### Firmware

Eu achei que teria mais problema nessa parte, mas ela é bem tranquila. 
Provavelmente você vai fazer o flash diversas vezes, até se dar por satisfeito com uma configuração que te agrade. Então, não tenha medo de alterar e fazer o flash você tem acesso fácil ao botão reset e não vai ter dor de cabeça toda a vez.
O QMk tem uma ótima documentação, que te dá diversas opções de como fazer a mesma coisa. Se for usuário Windows ou Mac tem ainda um toolkit.

A melhor dica que posso dar: use o [configurador online](https://config.qmk.fm/#/). Assim você pode vizualizar as teclas e ter mais ideias de atalhos e modificadores do que você vai gostar e que vai funcionar para você.
Lembrando que o modelo que você procura no configurador online é o /handwired/dactyl_manuform/5x6.
Se quiser, pode usar a minha configuração como base: [keymap.json](dezzare/keymap.json). Basta fazer o upload no configurador e partir dali.



## License

Copyright © 2015-2017 Matthew Adereth and Tom Short

The source code for generating the models (everything excluding the [things/](things/) and [resources/](resources/) directories is distributed under the [GNU AFFERO GENERAL PUBLIC LICENSE Version 3](LICENSE).  The generated models and PCB designs are distributed under the [Creative Commons Attribution-NonCommercial-ShareAlike License Version 3.0](LICENSE-models).
