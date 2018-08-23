---
title: PROFILE_CURRENTID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PROFILE_CURRENTID
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6509645be235c0ca1804b913ccd13e69dbabb770
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671596"
---
# <a name="profilecurrentid"></a>PROFILE_CURRENTID
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [PROFILE_CURRENTID](https://docs.microsoft.com/visualstudio/profiling/profile-currentid).  
  
PROFILE_CURRENTID vrátí pseudo token pro id vlákna nebo id procesu, ve volání funkce NameProfile StartProfile, StopProfile, SuspendProfile a ResumeProfile. Použijte ho, aby funkce, který má použít pro aktuální vlákno nebo proces, nikoli konkrétně uvedené jeden.  
  
## <a name="example"></a>Příklad  
 PROFILE_CURRENTID je definována v VSPerf.h jako:  
  
```  
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje PROFILE_CURRENTID. V příkladu se používá jako parametr určující aktuální vlákno ve volání PROFILE_CURRENTID [StartProfile](../profiling/startprofile.md) funkce.  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [Reference k rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [NameProfile](../profiling/nameprofile.md)   
 [ResumeProfile](../profiling/resumeprofile.md)   
 [StartProfile](../profiling/startprofile.md)   
 [StopProfile](../profiling/stopprofile.md)   
 [SuspendProfile](../profiling/suspendprofile.md)



