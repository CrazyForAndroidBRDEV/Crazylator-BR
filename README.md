# Crazylator BR

[![Downloads](https://img.shields.io/github/downloads/CrazyForAndroidBR/Crazylator-BR/total?style=for-the-badge&label=downloads)](https://github.com/CrazyForAndroidBR/Crazylator-BR/releases)
[![Latest release](https://img.shields.io/github/v/release/CrazyForAndroidBR/Crazylator-BR?style=for-the-badge&label=latest)](https://github.com/CrazyForAndroidBR/Crazylator-BR/releases/latest)

**Crazylator BR** é um emulador de ambiente Windows para Android, desenvolvido para executar jogos e aplicativos de PC em celulares compatíveis. O projeto organiza cada ambiente em **containers independentes**, permitindo configurar drivers gráficos, Wine, Box64, resolução, áudio, controles e componentes do Windows separadamente.

> Este projeto é distribuído em versão beta. O desempenho e a compatibilidade dependem do aparelho, da GPU, da memória disponível, do driver selecionado e do jogo executado.

## Download

O APK beta está disponível na seção [Releases](https://github.com/CrazyForAndroidBR/Crazylator-BR/releases). O arquivo incluído neste repositório é `Crazylator-BR-Beta.apk`.

Para instalar manualmente, baixe o APK no Android, autorize a instalação de aplicativos de fontes desconhecidas quando o sistema solicitar e instale o arquivo. Antes de testar uma atualização, faça uma cópia dos seus containers importantes.

## Principais recursos

### Containers para jogos e aplicativos

Cada container funciona como um ambiente separado. É possível criar, editar, duplicar e remover containers, mantendo configurações diferentes para jogos distintos. Os containers podem armazenar nome, resolução, drivers, wrappers gráficos, áudio, versão do Wine, componentes do Windows, variáveis de ambiente, unidades virtuais e afinidade de processador.

### Ambiente Wine para Android

O Crazylator BR utiliza o Wine para fornecer compatibilidade com programas e jogos de Windows. A interface permite instalar e selecionar versões do Wine, ajustar componentes, configurar registro e definir a versão do Windows usada pelo ambiente.

### Box64 e execução de aplicativos x86/x64

O projeto inclui gerenciamento de versões e presets do Box64. O usuário pode selecionar perfis de desempenho, configurar afinidade de CPU e ajustar o comportamento de aplicativos de 32 bits e 64 bits quando essas opções estiverem disponíveis no aparelho.

### Drivers gráficos e wrappers

O aplicativo oferece configuração de drivers gráficos e camadas de tradução, incluindo opções relacionadas a Vulkan, OpenGL, Turnip, Vortek, Gladio, DXVK, VKD3D e WineD3D, conforme os componentes instalados no APK e no container. As opções disponíveis podem variar de acordo com o dispositivo e com a versão dos drivers.

- **Vulkan e OpenGL:** escolha do caminho gráfico compatível com o aparelho.
- **Turnip e AdrenoTools:** opções direcionadas principalmente a dispositivos Qualcomm Snapdragon com GPU Adreno.
- **DXVK:** tradução de Direct3D para Vulkan em jogos compatíveis.
- **VKD3D:** suporte para caminhos baseados em Direct3D 12 e Vulkan.
- **WineD3D:** alternativa baseada em OpenGL para compatibilidade com determinados jogos.
- **Configuração de drivers:** ajustes separados para o driver gráfico e para o wrapper utilizado pelo jogo.

### GenMali

O **GenMali** é um perfil experimental de desempenho para aparelhos com GPU ARM Mali. Quando ativado, pode aplicar uma combinação de ajustes voltada a esse tipo de GPU, incluindo perfil de desempenho do Box64, afinidade de CPU e configurações de driver disponíveis no ambiente.

> **Atenção:** as opções GenMali e as demais otimizações para GPU Mali são experimentais. O resultado depende do modelo do celular, da geração da GPU, da versão do Android, do driver Vulkan, da memória disponível e do jogo. Em alguns aparelhos pode não haver ganho, e em outros a compatibilidade pode piorar. Teste uma opção por vez e desative-a se o jogo apresentar travamentos, tela preta, artefatos ou fechamento inesperado.

### Otimização Snapdragon/Adreno

A **Otimização Snapdragon/Adreno** foi criada para aparelhos Qualcomm Snapdragon equipados com GPU Adreno. Ela pode ajustar o caminho de execução, o Box64 e a compilação de shaders para reduzir engasgos ou melhorar a estabilidade em determinados jogos.

Essa função não garante aumento de FPS. O resultado depende do driver usado, do jogo, do modelo da GPU, da temperatura e do limite de energia do aparelho. Não é recomendado ativá-la em dispositivos com GPU Mali.

### Otimização para pouca RAM

A **Otimização para pouca RAM** identifica aparelhos com memória limitada e pode aplicar ajustes para reduzir o uso de memória durante a execução. Entre os possíveis ajustes estão um preset mais leve do Box64, caches menores de textura e ajustes de cache de shaders.

Ela pode ajudar a reduzir encerramentos causados pelo sistema em celulares com pouca memória. Em aparelhos com bastante RAM, entretanto, reduzir caches pode não trazer benefício e pode aumentar carregamentos ou engasgos. Ative-a somente quando houver necessidade.

### Desempenho e compatibilidade GameHub

O perfil **Desempenho e compatibilidade GameHub** reúne ajustes opcionais para situações específicas, como apresentação de frames, sincronização, compilação de shaders, compatibilidade e perfis direcionados a determinados jogos.

Entre as funções relacionadas estão:

- apresentação segura com prioridade para compatibilidade;
- estabilização de frame pacing;
- compilação assíncrona do DXVK quando suportada;
- perfis de compatibilidade para jogos específicos;
- ajustes de transcodificação BCN em dispositivos Mali;
- ajustes experimentais de desempenho que devem ser avaliados individualmente.

### Áudio, controles e periféricos

O Crazylator BR permite selecionar drivers de áudio, configurar controles, mapear gamepads e ajustar dispositivos de entrada. Também há suporte para clipboard entre Android e Wine e para abertura de arquivos externos dentro de um container, quando compatível com o ambiente.

### Desktop e HUD

O ambiente inclui configurações de desktop, tema claro ou escuro, plano de fundo, fonte do sistema, modo HUD e controles de interface. A interface recebeu um tema escuro com elementos ciano e azul, mantendo foco em leitura e navegação durante o uso em telas pequenas.

### Unidades, arquivos e variáveis de ambiente

Cada container pode trabalhar com unidades virtuais, caminhos de arquivos, variáveis de ambiente e atalhos. Isso facilita separar arquivos de jogos, configurações e componentes de ambientes diferentes.

### Registro e componentes do Windows

O aplicativo possui telas para configuração do Wine, componentes do Windows, registro, canais de depuração, logs e parâmetros avançados. Essas opções devem ser alteradas com cuidado, porque uma combinação incompatível pode impedir um jogo de abrir.

## Compatibilidade e desempenho

O Crazylator BR não oferece o mesmo resultado em todos os aparelhos. O desempenho é influenciado por:

- modelo e arquitetura do processador;
- GPU e driver Vulkan/OpenGL;
- quantidade de RAM disponível;
- versão do Android;
- resolução escolhida;
- versão do Wine;
- wrapper gráfico selecionado;
- preset do Box64;
- temperatura e gerenciamento de energia;
- requisitos do jogo.

Para reduzir problemas, comece com as configurações padrão, use um container separado para cada jogo e ative apenas uma otimização por vez. Se ocorrer crash, tela preta, áudio falhando ou queda de desempenho, volte ao perfil anterior e teste outro driver ou wrapper.

## Avisos importantes

- O APK é uma versão beta e pode conter falhas.
- As otimizações GenMali e as opções voltadas a GPU Mali são experimentais.
- Uma opção que melhora um jogo pode piorar outro.
- Não existe garantia de compatibilidade com todos os jogos ou aparelhos.
- Não publique chaves privadas, keystores ou senhas junto com o APK.
- Distribua o projeto somente se você tiver autorização para modificar e redistribuir a base original, os componentes e os arquivos incluídos.
- Faça backup dos containers antes de instalar atualizações.

## Canal do desenvolvedor

Acompanhe novidades, testes, tutoriais e atualizações no canal **Crazy for Android BR**:

[https://youtube.com/@crazyforandroidbr4644?si=Y04r553HxtrM0Fy7](https://youtube.com/@crazyforandroidbr4644?si=Y04r553HxtrM0Fy7)

## Estrutura do repositório

```text
.
├── Crazylator-BR-Beta.apk
└── README.md
```

## Licença e créditos

O crédito desta edição é de **Crazy for Android BR DEV**. Consulte as licenças dos componentes de terceiros antes de redistribuir o APK ou publicar versões derivadas.

## Referências

[1]: https://youtube.com/@crazyforandroidbr4644?si=Y04r553HxtrM0Fy7 "Canal Crazy for Android BR"
[2]: https://github.com/CrazyForAndroidBR/Crazylator-BR/releases "Releases do Crazylator BR"
