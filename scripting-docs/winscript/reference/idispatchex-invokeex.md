---
title: IDispatchEx::InvokeEx | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.InvokeEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- InvokeEx method
ms.assetid: d90783e6-4b89-4423-8a56-a9c8b4b2c813
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a15acb3211c0d3dd19c0d262efb6cbd3327ab9a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575315"
---
# <a name="idispatchexinvokeex"></a>IDispatchEx::InvokeEx
Fornece acesso a propriedades e métodos expostos por um objeto `IDispatchEx`.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp
HRESULT InvokeEx(  
   DISPID id,  
   LCID lcid,  
   WORD wFlags,  
   DISPARAMS *pdp,  
   VARIANT *pVarRes,   
   EXCEPINFO *pei,   
   IServiceProvider *pspCaller   
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `id`  
 Identifica o membro. Usa `GetDispID` ou `GetNextDispID` para obter o identificador de expedição.  
  
 `lcid`  
 O contexto de localidade no qual interpretar argumentos. O `lcid` é passado para `InvokeEx` para permitir que o objeto interprete seus argumentos específicos para uma localidade.  
  
 `wFlags`  
 Os valores válidos para `wFlags` são:  
  
 DISPATCH_PROPERTYGET &#124; DISPATCH_METHOD &#124; DISPATCH_PROPERTYPUT &#124; DISPATCH_PROPERTYPUTREF &#124; DISPATCH_CONSTRUCT  
  
 Sinalizadores que descrevem o contexto da chamada de `InvokeEx`:  
  
|Valor|Significado|  
|-----------|-------------|  
|DISPATCH_METHOD|O membro é invocado como um método. Se uma propriedade tiver o mesmo nome, isso e o sinalizador de DISPATCH_PROPERTYGET poderão ser definidos (definidos por `IDispatch`).|  
|DISPATCH_PROPERTYGET|O membro é recuperado como uma propriedade ou um membro de dados (definido por `IDispatch`).|  
|DISPATCH_PROPERTYPUT|O membro é alterado como um membro de dados ou propriedade (definido por `IDispatch`).|  
|DISPATCH_PROPERTYPUTREF|O membro é alterado por uma atribuição de referência em vez de uma atribuição de valor. Esse sinalizador é válido somente quando a propriedade aceita uma referência a um objeto (definido por `IDispatch`).|  
|DISPATCH_CONSTRUCT|O membro está sendo usado como um construtor. (Esse é um novo valor definido por `IDispatchEx`). Os valores válidos para `wFlags` são:<br /><br /> DISPATCH_PROPERTYGET DISPATCH_METHOD DISPATCH_PROPERTYPUT DISPATCH_PROPERTYPUTREF DISPATCH_CONSTRUCT|  
  
 `pdp`  
 Ponteiro para uma estrutura contendo uma matriz de argumentos, uma matriz de DISPIDs de argumento para argumentos nomeados e contagens para o número de elementos nas matrizes. Consulte a documentação do `IDispatch` para obter uma descrição completa da estrutura DISPPARAMS.  
  
 `pVarRes`  
 Ponteiro para o local onde o resultado deve ser armazenado ou nulo se o chamador não espera nenhum resultado. Esse argumento será ignorado se DISPATCH_PROPERTYPUT ou DISPATCH_PROPERTYPUTREF for especificado.  
  
 `pei`  
 Ponteiro para uma estrutura que contém informações de exceção. Essa estrutura deve ser preenchida se `DISP_E_EXCEPTION` for retornada. Pode ser NULL. Consulte a documentação do `IDispatch` para obter uma descrição completa da estrutura de `EXCEPINFO`.  
  
 `pspCaller`  
 Ponteiro para um objeto de provedor de serviços fornecido pelo chamador, que permite que o objeto obtenha serviços do chamador. Pode ser NULL.  
  
 `IDispatchEx::InvokeEx` fornece todos os mesmos recursos que `IDispatch::Invoke` e adiciona algumas extensões:  
  
|||  
|-|-|  
|DISPATCH_CONSTRUCT|Indica que o item está sendo usado como um construtor.|  
|`pspCaller`|O `pspCaller` permite o acesso de objeto aos serviços fornecidos pelo chamador. Serviços específicos podem ser tratados pelo próprio chamador ou delegados a chamadores mais acima da cadeia de chamadas. Por exemplo, se um mecanismo de script dentro de um navegador fizer uma chamada de `InvokeEx` para um objeto externo, o objeto poderá seguir a cadeia de `pspCaller` para obter serviços do navegador ou mecanismo de script. (Observe que a cadeia de chamadas não é a mesma que a cadeia de criação — também conhecida como cadeia de contêiner ou cadeia de sites. A cadeia de criação pode estar disponível por meio de algum outro mecanismo, como `IObjectWithSite`.)|  
|Ponteiro `this`|Quando DISPATCH_METHOD é definido em `wFlags`, pode haver um "parâmetro nomeado" para o valor "This". O DISPID será DISPID_THIS e deverá ser o primeiro parâmetro nomeado.|  
  
 O parâmetro `riid` não usado no `IDispatch::Invoke` foi removido.  
  
 O parâmetro `puArgArr` no `IDispatch::Invoke` foi removido.  
  
 Consulte a documentação do `IDispatch::Invoke` para obter os exemplos a seguir:  
  
 "Chamando um método sem argumentos"  
  
 "Obtendo e definindo propriedades"  
  
 "Passando parâmetros"  
  
 "Propriedades indexadas"  
  
 "Gerando exceções durante invocação"  
  
 "Erros de retorno"  
  
## <a name="return-value"></a>Valor retornado  
 Retorna um dos seguintes valores:  
  
|||  
|-|-|  
|`S_OK`|Êxito.|  
|DISP_E_BADPARAMCOUNT|O número de elementos fornecidos para DISPPARAMS é diferente do número de argumentos aceitos pelo método ou propriedade.|  
|DISP_E_BADVARTYPE|Um dos argumentos em `rgvarg` não é um tipo de variante válido.|  
|DISP_E_EXCEPTION|O aplicativo precisa gerar uma exceção. Nesse caso, a estrutura passada em `pei` deve ser preenchida.|  
|DISP_E_MEMBERNOTFOUND|O membro solicitado não existe ou a chamada para `InvokeEx` tentou definir o valor de uma propriedade somente leitura.|  
|DISP_E_NONAMEDARGS|Esta implementação de `IDispatch` não oferece suporte a argumentos nomeados.|  
|DISP_E_OVERFLOW|Um dos argumentos em `rgvarg` não pôde ser forçado ao tipo especificado.|  
|DISP_E_PARAMNOTFOUND|Um dos DISPIDs de parâmetro não corresponde a um parâmetro no método.|  
|DISP_E_TYPEMISMATCH|Não foi possível forçar um ou mais argumentos.|  
|DISP_E_UNKNOWNLCID|O membro que está sendo invocado interpreta os argumentos da cadeia de caracteres de acordo com o LCID e o LCID não é reconhecido. Se o LCID não for necessário para interpretar argumentos, esse erro não deverá ser retornado.|  
|DISP_E_PARAMNOTOPTIONAL|Um parâmetro necessário foi omitido.|  
  
## <a name="example"></a>Exemplo  
  
```cpp
VARIANT var;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
   DISPPARAMS dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
   {  
      pdex->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
   }  
```  
  
## <a name="see-also"></a>Consulte também  
   de [interface IDispatchEx](../../winscript/reference/idispatchex-interface.md)  
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)