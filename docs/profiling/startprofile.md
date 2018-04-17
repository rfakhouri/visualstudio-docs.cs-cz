---
title: StartProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- StartProfile
ms.assetid: 1761311d-c9d5-48f5-b1f8-b3605829940a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f07c1be8fdc35a3aea4f09a3af04a583236e109
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="startprofile"></a>StartProfile
`StartProfile` Funkce nastaví čítač na hodnotu 1 (zapnuto) pro zadané profilování úrovni.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI StartProfile(  
                        PROFILE_CONTROL_LEVEL Level,   
                        unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Level`  
  
 Informuje o úrovni profilu, které výkon shromažďování dat lze použít. Následující **PROFILE_CONTROL_LEVEL** výčty slouží k označení jednu ze tří úrovní, které výkon lze použít shromažďování dat:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globální nastavení úrovně ovlivňuje všechny procesy a vláken v profilaci spustit.|  
|PROFILE_PROCESSLEVEL|Nastavení úrovně proces ovlivňuje všechna vlákna, které jsou součástí určený proces.|  
|PROFILE_THREADLEVEL|Přístup z více vláken profilace nastavení úrovně ovlivňuje zadaný vlákno.|  
  
 `dwId`  
  
 Identifikátor procesu nebo vlákno generované systémem.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch či neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Vrácená hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_ERROR_ID_NOEXIST|Profilování ID elementu neexistuje.|  
|PROFILE_ERROR_LEVEL_NOEXIST|Profilace Zadaná úroveň neexistuje.|  
|PROFILE_ERROR_MODE_NEVER|Profilování režimu byl nastaven na nikdy, při volání funkce.|  
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Profilaci volání funkce, profilaci úroveň nebo kombinaci volání a úroveň není dosud implementována.|  
|PROFILE_OK|Bylo volání úspěšné.|  
  
## <a name="remarks"></a>Poznámky  
 Stav spuštění a zastavení profilování úroveň řízení StartProfile a StopProfile. Spuštění a zastavení výchozí hodnota je 1. Počáteční hodnota lze změnit v registru. Každé volání StartProfile nastaví spuštění a zastavení na 1; každé volání StopProfile ji nastaví na hodnotu 0.  
  
 Při spuštění a zastavení je větší než 0, je stav spuštění a zastavení úroveň ON. Pokud je menší než nebo rovno 0, stav spuštění a zastavení je VYPNUTÝ.  
  
 Po spuštění a zastavení stav a stav pozastavení nebo obnovení se i na profilování stav pro úroveň je ON. Vlákna na profilovaným, proces globální, a úrovně stavy vláken pro vlákno musí být ON.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
 Hlavičky: V VSPerf.h deklarována  
  
 Import knihovny: VSPerf.lib  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje volání funkce StartProfile.  
  
```  
void ExerciseStartProfile()  
{  
    // StartProfile and StopProfile control the  
    // Start/Stop state for the profiling level.   
    // The default initial value of Start/Stop is 1.   
    // The initial value can be changed in the registry.   
    // Each call to StartProfile sets Start/Stop to 1;   
    // each call to StopProfile sets it to 0.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold return value of   
    // the call to StartProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = StartProfile(  
        PROFILE_THREADLEVEL,  
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
 [Referenční dokumentace rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)