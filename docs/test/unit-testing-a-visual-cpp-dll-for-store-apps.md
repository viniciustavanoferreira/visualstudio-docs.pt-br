---
title: Como testar um DLL C++ para aplicativos UWP
ms.date: 05/01/2019
ms.topic: conceptual
ms.author: corob
manager: jillfra
ms.workload:
- uwp
author: corob-msft
ms.openlocfilehash: 540ff59838343988e7a27f42f8a10d723de1f649
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77274450"
---
# <a name="how-to-test-a-c-dll"></a>Como testar uma DLL C++

Este tópico descreve uma maneira de criar testes de unidade para uma DLL do C++ para aplicativos UWP (Plataforma Universal do Windows) com o Microsoft Test Framework para C++. A DLL RooterLib demonstra memórias vagas da teoria de limite do cálculo implementando uma função que calcula uma estimativa da raiz quadrada de um determinado número. A DLL, em seguida, pode ser incluída em um aplicativo UWP que mostra a um usuário as coisas divertidas que podem ser feitas com matemática.

Este tópico demonstra como usar teste de unidade como a primeira etapa do desenvolvimento. Nessa abordagem, primeiramente, você escreve um método de teste que verifique um comportamento específico no sistema que está sendo testado e, em seguida, escreve um código que passe no teste. Ao fazer alterações na ordem dos procedimentos a seguir, é possível reverter essa estratégia para primeiro escrever o código que deseja testar e depois escrever as unidades de teste.

Este tópico também cria uma única solução do Visual Studio e projetos separados para os testes de unidade e a DLL que você deseja testar. Também é possível incluir os testes de unidade diretamente no projeto de DLL ou criar soluções separadas para os testes de unidade e a .DLL. Consulte [Adicionar teste de unidade de aplicativos C++ existentes](../test/how-to-use-microsoft-test-framework-for-cpp.md) para obter dicas sobre a estrutura a ser usada.

## <a name="create-the-solution-and-the-unit-test-project"></a><a name="Create_the_solution_and_the_unit_test_project"></a>Crie a solução e o projeto de teste unitário

::: moniker range="vs-2019"

Comece criando um novo projeto de teste. No menu **Arquivo**, escolha **Novo** > **Projeto**. Na caixa de diálogo **Criar um novo projeto**, digite "teste" na caixa de pesquisa e, em seguida, defina **Linguagem de programação** como C++. Em seguida, escolha **Aplicativo de Teste de Unidade (Windows Universal)** na lista de modelos de projeto.

   ![Criar um novo projeto de teste do UWP](media/vs-2019/cpp-new-uwp-test-project-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

Comece criando um novo projeto de teste. No menu **Arquivo**, escolha **Novo** > **Projeto**. Na caixa de diálogo **Novo projeto**, expanda **Instalado** > **Visual C++** e escolha **Windows Universal**. Em seguida, escolha **Aplicativo de Teste de Unidade (Windows Universal)** na lista de modelos de projeto.

::: moniker-end

1. Na caixa de diálogo Novo projeto, expanda **Instalado** > **Visual C++** e escolha **Windows Universal**. Em seguida, escolha **Aplicativo de Teste de Unidade (Windows Universal)** na lista de modelos de projeto.

2. Dê ao projeto o nome `RooterLibTests`; especifique o local, dê à solução o nome `RooterLib`; e certifique-se de que a opção **Criar diretório para solução** esteja selecionada.

     ![Especifique o nome da solução e do projeto e o local](../test/media/ute_cpp_windows_unittestlib_createspecs.png)

3. No novo projeto, abra **unittest1.cpp**.

     ![unittest1.cpp](../test/media/ute_cpp_windows_unittest1_cpp.png)

     Observe que:

    - Cada teste é definido usando `TEST_METHOD(YourTestName){...}`.

         Você não precisa gravar uma assinatura de função convencional. A assinatura é criada pela macro TEST_METHOD. A macro gera uma função de instância que retorna void. Também gera uma função estática que retorna informações sobre o método de teste. Essas informações permitem que o Gerenciador de Testes encontrem o método.

    - Os métodos de teste são agrupados em classes usando `TEST_CLASS(YourClassName){...}`.

         Quando os testes são executados, uma instância de cada classe de teste é criada. Os métodos de teste são chamados em uma ordem não especificada. Você pode definir métodos especiais que são invocados antes e depois de cada módulo, classe ou método. Para obter mais informações, confira [Usando o Microsoft.VisualStudio.TestTools.CppUnitTestFramework](how-to-use-microsoft-test-framework-for-cpp.md).

## <a name="verify-that-the-tests-run-in-test-explorer"></a><a name="Verify_that_the_tests_run_in_Test_Explorer"></a>Verifique se os testes são executados no Test Explorer

1. Insira algum código de teste:

    ```cpp
    TEST_METHOD(TestMethod1)
    {
        Assert::AreEqual(1,1);
    }
    ```

     Observe que a classe `Assert` fornece vários métodos estáticos que você pode usar para verificar os resultados em métodos de teste.

2. No menu **Testar**, escolha **Executar** e **Executar Todos**.

     O projeto de teste é compilado e executado. A janela **Test Explorer** aparece e o teste é listado em **Testes Aprovados**. O painel **Resumo** na parte inferior da janela fornece detalhes adicionais sobre o teste selecionado.

     ![Gerenciador de Testes](../test/media/ute_cpp_testexplorer_testmethod1.png)

## <a name="add-the-dll-project-to-the-solution"></a><a name="Add_the_DLL_project_to_the_solution"></a>Adicione o projeto DLL à solução

::: moniker range="vs-2019"

No **Gerenciador de Soluções**, escolha o nome da solução. No menu de atalho, escolha **Adicionar** e, em seguida, **Novo projeto**. Na caixa de diálogo **Adicionar um novo projeto**, defina **Linguagem de programação** como C++ e digite "DLL" na caixa de pesquisa. Na lista de resultados, escolha **Aplicativo de teste de unidade (Universal Windows – C++/CX)**.

![Criar o projeto RooterLib](../test/media/vs-2019/cpp-new-uwp-test-project-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"
No **Gerenciador de Soluções**, escolha o nome da solução. No menu de atalho, escolha **Adicionar** e, em seguida, **Novo projeto**.

![Criar o projeto RooterLib](../test/media/ute_cpp_windows_rooterlib_create.png)

::: moniker-end

1. Na caixa de diálogo **Adicionar Novo Projeto**, escolha **DLL (aplicativos UWP)**.

2. Adicione o código a seguir ao arquivo *RooterLib.h*:

    ```cpp
    // The following ifdef block is the standard way of creating macros which make exporting
    // from a DLL simpler. All files within this DLL are compiled with the ROOTERLIB_EXPORTS
    // symbol defined on the command line. This symbol should not be defined on any project
    // that uses this DLL. This way any other project whose source files include this file see
    // ROOTERLIB_API functions as being imported from a DLL, whereas this DLL sees symbols
    // defined with this macro as being exported.
    #ifdef ROOTERLIB_EXPORTS
    #define ROOTERLIB_API  __declspec(dllexport)
    #else
    #define ROOTERLIB_API __declspec(dllimport)
    #endif //ROOTERLIB_EXPORTS

    class ROOTERLIB_API CRooterLib {
    public:
        CRooterLib(void);
        double SquareRoot(double v);
    };
    ```

     Os comentários explicam o bloco ifdef não apenas ao desenvolvedor da dll, mas também a qualquer pessoa que faça referência à DLL em seu projeto. Você pode adicionar o símbolo ROOTERLIB_EXPORTS à linha de comando usando as propriedades do projeto da DLL.

     A classe `CRooterLib` declara um construtor e o método avaliador `SqareRoot`.

3. Adicione o símbolo ROOTERLIB_EXPORTS à linha de comando.

    1. No **Gerenciador de Soluções**, escolha o projeto **RooterLib** e, em seguida, escolha **Propriedades** no menu de atalho.

         ![Adicionar uma definição de símbolo de pré-processador](../test/media/ute_cpp_windows_addpreprocessorsymbol.png)

    2. Na caixa de diálogo **Página de Propriedades de RooterLib**, expanda **Propriedades de Configuração**, expanda **C++** e escolha **Pré-processador**.

    3. Escolha ** \<Editar...>** na lista **Dedefinições de pré-processador** e, em seguida, adicione `ROOTERLIB_EXPORTS` a caixa de diálogo **Definições de pré-processador.**

4. Adicione implementações mínimas das funções declaradas. Abra *RooterLib.cpp* e adicione o seguinte código:

    ```cpp
    // constructor
    CRooterLib::CRooterLib()
    {
    }

    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        return 0.0;
    }

    ```

## <a name="make-the-dll-functions-visible-to-the-test-code"></a><a name="make_the_dll_functions_visible_to_the_test_code"></a> Tornar as funções de dll visíveis para o código de teste

1. Adicione RooterLib ao projeto RooterLibTests.

   1. No **Gerenciador de Soluções**, escolha o projeto **RooterLibTests** e, em seguida, escolha **Adicionar** > **Referência** no menu de atalho.

   1. Na caixa de diálogo **Adicionar Referência**, escolha **Projetos**. Então selecione o item **RouterLib**.

2. Inclua o arquivo de cabeçalho RooterLib em *unittest1.cpp*.

   1. Abra *unittest1.cpp*.

   2. Adicione esse código abaixo da linha `#include "CppUnitTest.h"`:

       ```cpp
       #include "..\RooterLib\RooterLib.h"
       ```

3. Adicione um teste que use a função importada. Adicione o seguinte código ao *unittest1.cpp:*

   ```cpp
   TEST_METHOD(BasicTest)
   {
       CRooterLib rooter;
       Assert::AreEqual(
           // Expected value:
           0.0,
           // Actual value:
           rooter.SquareRoot(0.0),
           // Tolerance:
           0.01,
           // Message:
           L"Basic test failed",
           // Line number - used if there is no PDB file:
           LINE_INFO());
   }
   ```

4. Compile a solução.

    O novo teste aparece no **Test Explorer** no nó Testes **não executados.**

5. No **Gerenciador de Testes**, escolha **Executar Todos**.

    ![Êxito no Teste básico](../test/media/ute_cpp_testexplorer_basictest.png)

   Você configurou o teste e os projetos de código, além de ter verificado que pode executar testes que executam funções no projeto de código. Agora, você pode começar a escrever testes e códigos reais.

## <a name="iteratively-augment-the-tests-and-make-them-pass"></a><a name="Iteratively_augment_the_tests_and_make_them_pass"></a>Aumentar iterativamente os testes e fazê-los passar

1. Adicione um novo teste:

    ```cpp
    TEST_METHOD(RangeTest)
    {
        CRooterLib rooter;
        for (double v = 1e-6; v < 1e6; v = v * 3.2)
        {
            double expected = v;
            double actual = rooter.SquareRoot(v*v);
            double tolerance = expected/1000;
            Assert::AreEqual(expected, actual, tolerance);
        }
    };
    ```

    > [!TIP]
    > É recomendável não alterar testes que tenham sido aprovados. Em vez disso, adicione um novo teste, atualize o código para que o teste seja aprovado e adicione outro teste, e assim por diante.
    >
    > Quando os usuários alterarem os respectivos requisitos, desabilite os testes que não estejam mais corretos. Escreva novos testes e faça-os funcionar, um por vez, da mesma maneira incremental.

2. No **Gerenciador de Testes**, escolha **Executar Todos**.

3. O teste falhará.

     ![Falha de RangeTest](../test/media/ute_cpp_testexplorer_rangetest_fail.png)

    > [!TIP]
    > Verifique se os testes falham imediatamente após escrevê-los. Isso ajuda a impedir a facilidade de errar ao escrever um teste que nunca falha.

4. Aprimore o código sob teste para que o novo teste seja aprovado. Adicione o seguinte ao *RooterLib.cpp*:

    ```cpp
    #include <math.h>
    ...
    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        double result = v;
        double diff = v;
        while (diff > result/1000)
        {
            double oldResult = result;
            result = result - (result*result - v)/(2*result);
            diff = abs (oldResult - result);
        }
        return result;
    }

    ```

5. Construa a solução e, em seguida, no **Test Explorer,** escolha **Executar tudo**.

     Ambos os testes são aprovados.

> [!TIP]
> Desenvolva o código adicionando testes, um de cada vez. Verifique se todos os testes passaram após cada iteração.

## <a name="debug-a-failing-test"></a><a name="Debug_a_failing_test"></a>Depurar um teste de falha

1. Adicionar outro teste a *unittest1.cpp*:

   ```cpp
   // Verify that negative inputs throw an exception.
    TEST_METHOD(NegativeRangeTest)
    {
      wchar_t message[200];
      CRooterLib rooter;
      for (double v = -0.1; v > -3.0; v = v - 0.5)
      {
        try
        {
          // Should raise an exception:
          double result = rooter.SquareRoot(v);

          swprintf_s(message, L"No exception for input %g", v);
          Assert::Fail(message, LINE_INFO());
        }
        catch (std::out_of_range ex)
        {
          continue; // Correct exception.
        }
        catch (...)
        {
          swprintf_s(message, L"Incorrect exception for %g", v);
          Assert::Fail(message, LINE_INFO());
        }
      }
   };
   ```

2. No **Gerenciador de Testes**, escolha **Executar Todos**.

    O teste falhará. Escolha o nome de teste no **Test Explorer**. A asserção com falha é realçada. A mensagem de falha fica visível no painel de detalhes do **Gerenciador de Testes**.

    ![Falha de NegativeRangeTests](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png)

3. Para ver o motivo da falha do teste, percorra a função:

   1. Defina o ponto de interrupção no início da função `SquareRoot`.

   2. No menu de atalho do teste com falha, escolha **Depurar Testes Selecionados**.

        Quando a execução for interrompida no ponto de interrupção, percorra o código.

   3. Adicione código ao *RooterLib.cpp* para capturar a exceção:

       ```cpp
       #include <stdexcept>
       ...
       double CRooterLib::SquareRoot(double v)
       {
           //Validate the input parameter:
           if (v < 0.0)
           {
             throw std::out_of_range("Can't do square roots of negatives");
           }
       ...

       ```

   1. No **Test Explorer,** escolha **Executar tudo** para testar o método corrigido e certifique-se de que você não introduziu uma regressão.

   Todos os testes agora foram aprovados.

   ![Todos os testes serão aprovados](../test/media/ute_ult_alltestspass.png)

## <a name="refactor-the-code-without-changing-tests"></a><a name="Refactor_the_code_without_changing_tests"></a>Refatorar o código sem alterar os testes

1. Simplifique o cálculo central na função `SquareRoot`:

    ```csharp
    // old code
    //result = result - (result*result - v)/(2*result);
    // new code
    result = (result + v/result) / 2.0;
    ```

2. Escolha **Executar Tudo** para testar o método refatorado e ter certeza de que você não introduziu uma regressão.

    > [!TIP]
    > Um conjunto estável de testes de unidade aprovados garante que você não introduziu bugs quando alterou o código.
    >
    > Mantenha a refatoração separada das outras alterações.
