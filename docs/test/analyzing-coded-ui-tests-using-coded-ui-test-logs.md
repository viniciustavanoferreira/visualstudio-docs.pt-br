---
title: Analisando testes de interface de usuário codificada usando logs de teste de interface de usuário codificada
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: ec1025eaa53861fae2cf92395d8842854649fa8c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75591210"
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Analisando testes de IU codificados usando logs de teste de IU codificado

Os logs de teste de IU codificado filtram e registram informações importantes sobre as execuções de teste de IU codificado. Os logs são apresentados em um formato que permite depurar os problemas rapidamente.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="step-1-enable-logging"></a>Etapa 1: Habilitar registro em log

De acordo com seu cenário, use um destes métodos para habilitar o log:

- Se não houver um arquivo *App.config* presente em seu projeto de teste:

   1. Determine qual processo *QTAgent\*.exe* é iniciado quando você executa o teste. Uma maneira de fazer isso é observar a guia **Detalhes** no **Gerenciador de Tarefas** do Windows.

   2. Abra o arquivo *.config* correspondente da *versão %ProgramFiles(x86)%\Microsoft Visual Studio\\\<>\\ \<edição>\Common7\IDE.* Por exemplo, se o processo que é executado é *QTAgent_40.exe*, abra *QTAgent_40.exe.config*.

   2. Modifique o valor de **EqtTraceLevel** para o nível de log desejado.

      ```xml
      <!-- You must use integral values for "value".
           Use 0 for off, 1 for error, 2 for warn, 3 for info, and 4 for verbose. -->
      <add name="EqtTraceLevel" value="4" />
      ```

   3. Salve o arquivo.

- Se houver um arquivo *App.config* presente em seu projeto de teste:

  - Abra o arquivo *App.config* no projeto e adicione o seguinte código sob o nó de configuração:

    ```xml
    <system.diagnostics>
      <switches>
        <add name="EqtTraceLevel" value="4" />
      </switches>
    </system.diagnostics>`
    ```

- Habilitar registro em log do próprio código de teste:

   ```csharp
   Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState = HtmlLoggerState.AllActionSnapshot;
   ```

## <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>Etapa 2: Execute o teste de IU codificado e veja o log

Ao executar um teste de IU codificado com as modificações no arquivo *QTAgent\*.exe.config* em vigor, você verá um link de saída nos resultados do **Gerenciador de Testes**. Os arquivos de log são produzidos não apenas quando o teste falha, mas também para testes bem-sucedidos quando o nível de rastreamento é definido como **verbose**.

1. No menu **Teste,** escolha **O Windows** e selecione **Test Explorer**.

2. No menu **Compilar**, escolha **Compilar Solução**.

3. No **Gerenciador de Testes**, selecione o teste de IU codificado que você deseja executar, abra seu menu de atalho e escolha em **Executar Testes Selecionados**.

     Os testes automatizados são executados e indicam se passaram ou falharam.

    > [!TIP]
    > Para exibir o **Gerenciador de Testes**, escolha **Teste** > **Windows** e escolha **Gerenciador de Testes**.

4. Clique no link **Saída** nos resultados do **Gerenciador de Testes**.

     ![Link de saída no Gerenciador de Testes](../test/media/cuit_htmlactionlog1.png)

     Essa ação exibe a saída do teste, que inclui um link ao log de ações.

     ![Resultados e links de saída do teste de IU codificado](../test/media/cuit_htmlactionlog2.png)

5. Escolha o link *UITestActionLog.html.*

     O log é exibido em seu navegador da Web.

     ![Arquivo de log do teste de IU codificado](../test/media/cuit_htmlactionlog3.png)

## <a name="see-also"></a>Confira também

- [Usar a automação da interface do usuário para testar o código](../test/use-ui-automation-to-test-your-code.md)
- [Como executar testes no Microsoft Visual Studio](https://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)
