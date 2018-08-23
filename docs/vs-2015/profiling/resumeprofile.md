---
title: ResumeProfile | Dokumentace Microsoftu
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
- ResumeProfile
ms.assetid: 876f145b-ec07-4240-ade6-4f6e44baadce
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95601212507f00904198750fe2d3547e481e5178
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629253"
---
# <a name="resumeprofile"></a>ResumeProfile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ResumeProfile](https://docs.microsoft.com/visualstudio/profiling/resumeprofile).  
  
`ResumeProfile` Čítač metoda sníží pozastavení/obnovení pro zadané úrovni profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI ResumeProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Level`  
  
 Informuje o úrovni profil, ke které výkonu shromažďování dat lze použít. Následující **PROFILE_CONTROL_LEVEL** enumerátory lze použít k označení jednu ze tří úrovní výkonu, které lze použít shromažďování dat:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globální nastavení úrovně má vliv na všechny procesy a vlákna při spuštění profilace.|  
|PROFILE_PROCESSLEVEL|Nastavení úrovně procesu mít vliv na všechna vlákna, které jsou součástí určeného procesu.|  
|PROFILE_THREADLEVEL|Vlákno profilace nastavení úrovně má vliv na zadaný podproces.|  
  
 `dwId`  
  
 Identifikátor procesu nebo vlákna generované systémem.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch nebo neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Návratová hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_ERROR_ID_NOEXIST|Profilace ID prvku neexistuje.|  
|PROFILE_ERROR_LEVEL_NOEXIST|Profilace Zadaná úroveň neexistuje.|  
|PROFILE_ERROR_MODE_NEVER|Režimu profilace byla nastavena na nikdy, když byla volána funkce.|  
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Profilace volání funkce, profilace úroveň nebo kombinací volání a úroveň není dosud implementována.|  
|PROFILE_OK|Volání bylo úspěšné.|  
  
## <a name="remarks"></a>Poznámky  
 Počáteční hodnota čítače pozastavení/obnovení je 0. Každé volání SuspendProfile přičte 1 k count pozastavit/pokračovat; každé volání ResumeProfile odečte 1.  
  
 Pokud je větší než 0. Počet pozastavení/obnovení, stav pozastavení/obnovení na úrovni je vypnuto. Pokud je počet nižší než nebo rovno 0, je do stavu pozastavit/pokračovat dále.  
  
 Po spuštění/zastavení stavu a stavu pozastavení/obnovení se i na profilování stav úrovně je ON. Pro vlákno bude profilována, procesu globální, a úrovni vlákna stavy pro vlákno musí být všechny ON.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
 Záhlaví: Deklarované v VSPerf.h  
  
 Knihovna importů: VSPerf.lib  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje funkci ResumeProfile. Příklad předpokládá, že volání metody SuspendProfile nebyly provedeny stejným vlákna nebo procesu identifikovaný [PROFILE_CURRENTID](../profiling/profile-currentid.md).  
  
```  
void ExerciseResumeProfile()  
{  
    // The initial value of the Suspend/Resume counter is 0.   
    // Each call to SuspendProfile adds 1 to the Suspend/Resume   
    // count; each call to ResumeProfile subtracts 1.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call to ResumeProfile  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = ResumeProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("ResumeProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Reference k rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)



