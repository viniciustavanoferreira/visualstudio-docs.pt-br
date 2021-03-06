---
title: Tarefa LIB | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.Name
- VC.Project.VCLibrarianTool.TreatLibWarningsAsErrors
- VC.Project.VCLibrarianTool.Verbose
- vc.task.lib
- VC.Project.VCLibrarianTool.ErrorReporting
- VC.Project.VCLibrarianTool.LinkLibraryDependencies
- VC.Project.VCLibrarianTool.LinkTimeCodeGeneration
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (C++), LIB task
- LIB task (MSBuild (C++))
ms.assetid: e062c7f9-cc69-4a83-9361-1bb5355e5fe8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5794d059a17f39531a7788895b604ae0e9590ce
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77633584"
---
# <a name="lib-task"></a>tarefa LIB

Envolve a ferramenta Microsoft 32-Bit Library Manager, *lib.exe*. O Gerenciador de Biblioteca cria e gerencia uma biblioteca de arquivos-objetos de formato COFF. O Gerenciador de Biblioteca também pode criar arquivos de exportação e importar bibliotecas para referenciar definições exportadas. Para obter mais informações, confira [Referência de LIB](/cpp/build/reference/lib-reference) e [Executando LIB](/cpp/build/reference/running-lib).

## <a name="parameters"></a>parâmetros

 A tabela a seguir descreve os parâmetros da tarefa **LIB**. A maioria dos parâmetros de tarefa corresponde a uma opção de linha de comando.

|Parâmetro|Descrição|
|---------------|-----------------|
|**AdditionalDependencies**|Parâmetro opcional **string[].**<br /><br /> Especifica itens adicionais para adicionar à linha de comando.|
|**AdditionalLibraryDirectories**|Parâmetro opcional **string[].**<br /><br /> Substitui o caminho da biblioteca de ambiente. Especifique um nome de diretório.<br /><br /> Para obter mais informações, consulte [/LIBPATH (Libpath Adicional)](/cpp/build/reference/libpath-additional-libpath).|
|**AdditionalOptions**|Parâmetro opcional **string.**<br /><br /> Uma lista de opções *lib.exe*, conforme especificado na linha de comando. Por exemplo, /\<option1> /\<option2> /\<option#>. Use esse parâmetro para especificar as opções de *lib.exe* que não são representadas por nenhum outro parâmetro de tarefa **LIB**.<br /><br /> Para obter mais informações, consulte [Executando LIB](/cpp/build/reference/running-lib).|
|**DisplayLibrary**|Parâmetro opcional **string.**<br /><br /> Exibe informações sobre a biblioteca de saída. Especifique um nome de arquivo para redirecionar as informações para um arquivo. Especifique "CON" ou não para redirecionar as informações para o console.<br /><br /> Esse parâmetro corresponde à opção **/LIST** de *lib.exe*.|
|**Errorreporting**|Parâmetro opcional **string.**<br /><br /> Especifica como enviar informações de erro internas para a Microsoft se *lib.exe* falhar no tempo de execução.<br /><br /> Especifique um dos valores a seguir, cada um correspondendo a uma opção de linha de comando.<br /><br /> -   **NoErrorReport** - **/ERRORREPORT:NONE**<br />-   **PromptImmediately** - **/ERRORREPORT:PROMPT**<br />-   **FilaParaNextLogin** - **/ERRORREPORT:QUEUE**<br />-   **Enviarrelatório de erro** - **/RELATÓRIO DE ERRO:ENVIAR**<br /><br /> Para obter mais informações, consulte a opção de linha de comando **/ERRORREPORT** em [Executando LIB](/cpp/build/reference/running-lib).|
|**ExportNamedFunctions**|Parâmetro opcional **string[].**<br /><br /> Especifica uma ou mais funções a serem exportadas.<br /><br /> Esse parâmetro corresponde à opção **/EXPORT** de *lib.exe*.|
|**ForceSymbolReferences**|Parâmetro opcional **string.**<br /><br /> Força o *lib.exe* a incluir uma referência ao símbolo especificado.<br /><br /> Esse parâmetro corresponde à opção **/INCLUDE:** de *lib.exe*.|
|**IgnoreAllDefaultLibraries**|Parâmetro `Boolean` opcional.<br /><br /> Se ele for `true`, removerá todas as bibliotecas padrão da lista de bibliotecas pesquisadas por *lib.exe* ao resolver referências externas.<br /><br /> Esse parâmetro corresponde ao formato sem parâmetros da opção **/NODEFAULTLIB** de *lib.exe*.|
|**IgnoreSpecificDefaultLibraries**|Parâmetro opcional **string[].**<br /><br /> Remove as bibliotecas especificadas da lista de bibliotecas pesquisadas pelo *lib.exe* ao resolver referências externas.<br /><br /> Esse parâmetro corresponde à opção **/NODEFAULTLIB** de *lib.exe*, que usa um argumento `library`.|
|**LinkLibraryDependencies**|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, especificará que as saídas de biblioteca das dependências do projeto serão vinculadas automaticamente.|
|**LinkTimeCodeGeneration**|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, especificará a geração do código de tempo de vinculação.<br /><br /> Esse parâmetro corresponde à opção **/LCTG** de *lib.exe*.|
|**MinimumRequiredVersion**|Parâmetro opcional **string.**<br /><br /> Especifica a versão mínima necessária do subsistema. Especifique uma lista delimitada por vírgulas de números decimais no intervalo de 0 a 65535.|
|**ModuleDefinitionFile**|Parâmetro opcional **string.**<br /><br /> Especifica o nome do arquivo de definição de módulo (*.def*).<br /><br /> Esse parâmetro corresponde à opção **/DEF** de *lib.exe*, que usa um argumento `filename`.|
|**Nome**|Parâmetro opcional **string.**<br /><br /> Ao compilar uma biblioteca de importação, especifica o nome da DLL para a qual a biblioteca de importação está sendo compilada.<br /><br /> Esse parâmetro corresponde à opção **/NAME** de *lib.exe*, que usa um argumento `filename`.|
|**Outputfile**|Parâmetro opcional **string.**<br /><br /> Substitui o nome padrão e o local do programa criado pelo *lib.exe*.<br /><br /> Esse parâmetro corresponde à opção **/OUT** de *lib.exe*, que usa um argumento `filename`.|
|**RemoveObjects**|Parâmetro opcional **string[].**<br /><br /> Omite o objeto especificado da biblioteca de saída. *Lib.exe* cria uma biblioteca de saída combinando todos os objetos (sejam em arquivos-objeto sejam em bibliotecas) e, em seguida, excluindo os objetos especificados por essa opção.<br /><br /> Esse parâmetro corresponde à opção **/REMOVE** de *lib.exe*, que usa um argumento `membername`.|
|**Fontes**|Parâmetro `ITaskItem[]` obrigatório.<br /><br /> Especifica uma lista de arquivos de origem separados por espaços.|
|**Subsistema**|Parâmetro opcional **string.**<br /><br /> Especifica o ambiente para o executável. A escolha do subsistema afeta o símbolo do ponto de entrada ou a função de ponto de entrada.<br /><br /> Especifique um dos valores a seguir, cada um correspondendo a uma opção de linha de comando.<br /><br /> -   **Console** - **/SUBSYSTEM:CONSOLE**<br />-   **Windows** - **/SUBSYSTEM:WINDOWS**<br />-   **Nativo** - **/SUBSYSTEM:NATIVE**<br />-   **Aplicativo EFI** - **/SUBSYSTEM:EFI_APPLICATION**<br />-   **Driver de serviço de inicialização EFI** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**<br />-   **ROM** - **/SUBSISTEMA EFI:EFI_ROM**<br />-   **Tempo de execução** - do EFI **/SUBSISTEMA:EFI_RUNTIME_DRIVER**<br />-   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**<br />-   **POSIX** - **/SUBSISTEMA:POSIX**<br /><br /> Para obter mais informações, confira [/SUBSYSTEM (Especificar subsistema)](/cpp/build/reference/subsystem-specify-subsystem).|
|**SuppressStartupBanner**|Parâmetro **booleano** opcional.<br /><br /> Se `true`, impedirá a exibição da mensagem de direitos autorais e de número de versão quando a tarefa for iniciada.<br /><br /> Para obter mais informações, consulte a opção **/NOLOGO** em [Executando LIB](/cpp/build/reference/running-lib).|
|**TargetMachine**|Parâmetro opcional **string.**<br /><br /> Especifica a plataforma de destino para o programa ou DLL.<br /><br /> Especifique um dos valores a seguir, cada um correspondendo a uma opção de linha de comando.<br /><br /> -   **MachineARM** - **/MÁQUINA:ARM**<br />-   **MachineEBC** - **/MACHINE:EBC**<br />-   **MachineIA64** - **/MACHINE:IA64**<br />-   **MACHINEMIPS** - **/MÁQUINA:MIPS**<br />-   **MACHINEMIPS16** - **/MÁQUINA:MIPS16**<br />-   **MachineMIPSFPU** -**/MACHINE:MIPSFPU**<br />-   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**<br />-   **MáquinasH4** - **/MÁQUINA:SH4**<br />-   **MachineTHUMB** - **/MACHINE:THUMB**<br />-   **MachineX64** - **/MÁQUINA:X64**<br />-   **MachineX86** - **/MÁQUINA:X86**<br /><br /> Para obter mais informações, confira [/MACHINE (Especificar plataforma de destino)](/cpp/build/reference/machine-specify-target-platform).|
|**TrackerLogDirectory**|Parâmetro opcional **string.**<br /><br /> Especifica o diretório de log de rastreamento.|
|**TreatLibWarningAsErrors**|Parâmetro **booleano** opcional.<br /><br /> Se ele for `true`, fará com que a tarefa **LIB** não gere um arquivo de saída se *lib.exe* gerar um aviso. Se `false`, um arquivo de saída será gerado.<br /><br /> Para obter mais informações, consulte a opção **/WX** em [Executando LIB](/cpp/build/reference/running-lib).|
|**UseUnicodeResponseFiles**|Parâmetro **booleano** opcional.<br /><br /> Se `true`, instruirá o sistema do projeto a gerar arquivos de resposta UNICODE quando o bibliotecário for gerado. Especifique `true` quando os arquivos no projeto tiverem caminhos UNICODE.|
|**Verbose**|Parâmetro **booleano** opcional.<br /><br /> Se ele for `true`, exibirá detalhes sobre o progresso da sessão; isso inclui os nomes dos arquivos *.obj* que estão sendo adicionados. A informação é enviada para uma saída padrão e pode ser redirecionada para um arquivo.<br /><br /> Para obter mais informações, consulte a opção **/VERBOSE** em [Executando LIB](/cpp/build/reference/running-lib).|

## <a name="see-also"></a>Confira também

- [Referência de tarefas](../msbuild/msbuild-task-reference.md)