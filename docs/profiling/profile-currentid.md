---
title: PROFILE_CURRENTID | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- PROFILE_CURRENTID
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 747922bf52bee18b20aeba95f7d549c890afceea
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599308"
---
# <a name="profilecurrentid"></a>PROFILE_CURRENTID
PROFILE_CURRENTID vrátí ID vlákna nebo ID procesu, ve volání funkce NameProfile StartProfile, StopProfile, SuspendProfile a ResumeProfile pseudo token. Použijte ho, aby funkce, který má použít pro aktuální vlákno nebo proces, nikoli konkrétně uvedené jeden.

## <a name="example"></a>Příklad
 PROFILE_CURRENTID je definována v *VSPerf.h* jako:

```cpp
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;
```

## <a name="example"></a>Příklad
 Následující příklad ukazuje PROFILE_CURRENTID. V příkladu se používá jako parametr určující aktuální vlákno ve volání PROFILE_CURRENTID [StartProfile](../profiling/startprofile.md) funkce.

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

## <a name="see-also"></a>Viz také:
- [Visual Studio profiler API reference (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)
- [NameProfile](../profiling/nameprofile.md)
- [ResumeProfile](../profiling/resumeprofile.md)
- [StartProfile](../profiling/startprofile.md)
- [StopProfile](../profiling/stopprofile.md)
- [SuspendProfile](../profiling/suspendprofile.md)