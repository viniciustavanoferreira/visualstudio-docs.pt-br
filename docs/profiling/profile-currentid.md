---
title: PROFILE_CURRENTID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- PROFILE_CURRENTID
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 63b44bee152acbf5529acfcadaa49a19e9feb52b
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778356"
---
# <a name="profile_currentid"></a>PROFILE_CURRENTID
O PROFILE_CURRENTID retorna o pseudotoken para a ID do thread ou a ID do processo, em uma chamada para as funções NameProfile StartProfile, StopProfile, SuspendProfile e ResumeProfile. Use-o para fazer com que a função opere no thread atual ou processo, em vez de um especificamente indicado.

## <a name="example"></a>Exemplo
 PROFILE_CURRENTID é definido em *VSPerf.h* como:

```cpp
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;
```

## <a name="example"></a>Exemplo
 O exemplo a seguir ilustra PROFILE_CURRENTID. O exemplo usa PROFILE_CURRENTID como um parâmetro que identifica o thread atual em uma chamada para a função [StartProfile](../profiling/startprofile.md).

```cpp
void ExerciseProfileCurrentID()
{
    // Declare ProfileOperationResult enumeration
    // to hold return value of a call to StartProfile.
    PROFILE_COMMAND_STATUS profileResult;

    // Variables used to print output.
    HRESULT hResult;
    TCHAR tchBuffer[256];

    profileResult = StartProfile(
        PROFILE_GLOBALLEVEL,
        PROFILE_CURRENTID);

    // Format and print result.
    LPCTSTR pszFormat = TEXT("%s %d.\0");
    TCHAR* pszTxt = TEXT("StartProfile returned");
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,
        pszTxt, profileResult);

#ifdef DEBUG
    OutputDebugString(tchBuffer);
#endif
}
```

## <a name="see-also"></a>Confira também
- [Referência de API do profiler do Visual Studio (nativa)](../profiling/visual-studio-profiler-api-reference-native.md)
- [NameProfile](../profiling/nameprofile.md)
- [ResumeProfile](../profiling/resumeprofile.md)
- [StartProfile](../profiling/startprofile.md)
- [StopProfile](../profiling/stopprofile.md)
- [SuspendProfile](../profiling/suspendprofile.md)
