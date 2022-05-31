##OS ARQUIVOS FINAIS ESTÃO NA PASTA SRC, AS PASTAS LAB-02 e LAB-03 MOSTRAM O HISTÓRICO de COMMITS##

Após a configuração do ambiente bare metal de desenvolvimento, o projeto para a criação do primeiro projeto "pisca LED" foi iniciado.

Durante a realização do Laboratório 2 os arquivos de partida foram criados juntamente ao processo de compilação para um sistema Cortex-M. Deste modo, iniciamos a craição de um firmware para piscar o LED integrado da placa STM32.
Este processo foi baseado na utilização de uma STM32F411 Blackpill.
Inicialmente criamos uma pasta para o novo projeto e criamos um arquivo main.c, compilado utilizando a arquitetura do compilador GNU Arm Embedded Toolchain, realizando a criação do arquivo main.o.
Utilizamos o comando make para realizar a compilação do arquivo, automatizada utilizando um arquivo Makefile. Após este processo, criamos o arquivo startup.c para realizar a rotina de execução das tarefas iniciais e essenciais para o funcionamento como: inicializar stacks, preparar os streams, etc.
Alteramos o Makefile para compilar o startup.c e alteramos o arquivo startup.c nas seções: declaração e inicialização do Stack, declaração e inicialização da Tabela de Vetores de Interrupção, código do Reset handler e outros códigos exception handler.
Deste modo, o Laboratório 2 está completo.

Durante a realização do Laboratório 3 modificamos os arquivos criados no Laboratório 2 para continuar o projeto "pisca LED", adicionando o arquivo linker script e gerando o map file.
Inicialmente os arquivos do Laboratório 2 foram copiados para uma nova pasta "lab-03" para serem utilizados. Através do datasheet da placa de desenvolvimento verificamos que o pino PC13 esta conectado ao LED e começamos a configuração de clock para habilitar a porta GPIOC e definir o PC13 como pino de saída nos registradores de periférico do GPIOC.
Depois disso, utilizamos a "ferramenta arm-none-eabi-objdump" para analisar o main.o e suas seções. Após este processo realizamos a craição do arquivo linker script para combinar os arquivos objetos de modo a combiná-los em um único arquivo executável. Descrevemos neste arquivo as regiões de memória disponíveis e exportamos os símbolos para carregar os dados da FLASH para SRAM.
Por fim, adicionamos uma nova regra para o arquivo de saída blinky.elf para realizar o processo de linking automaticamente por meio do Makefile.
Deste modo, o Laboratório 3 está completo.
