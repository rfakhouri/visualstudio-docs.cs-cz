---
title: ResumeProfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ResumeProfile
ms.assetid: 876f145b-ec07-4240-ade6-4f6e44baadce
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 899c39af318e16465ccd36d671a2c9d7305b431d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="resumeprofile"></a>ResumeProfile
`ResumeProfile` Metoda snižuje pozastavit nebo obnovit čítač pro zadané profilování úrovni.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI ResumeProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Level`  
  
 Informuje o úrovni profilu, které výkon shromažďování dat lze použít. Následující **PROFILE_CONTROL_LEVEL** výčty slouží k označení jednu ze tří úrovní, které výkon lze použít shromažďování dat:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globální nastavení úrovně ovlivňuje všechny procesy a vláken v profilaci spustit.|  
|PROFILE_PROCESSLEVEL|Nastavení úrovně proces ovlivnit všechna vlákna, které jsou součástí určený proces.|  
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
 Počáteční hodnota čítače pozastavení nebo obnovení je 0. Každé volání SuspendProfile přidá 1 k count pozastavit nebo obnovit; každé volání ResumeProfile odečítá od 1.  
  
 Pokud počet pozastavení nebo obnovení je větší než 0, je stav pozastavení nebo obnovení na úrovni OFF. Pokud je počet je menší než nebo rovna 0, pozastavit nebo obnovit stav je ON.  
  
 Po spuštění a zastavení stav a stav pozastavení nebo obnovení se i na profilování stav pro úroveň je ON. Vlákna na profilovaným, proces globální, a úroveň vlákno stavy pro vlákno musí být ON.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
 Hlavičky: V VSPerf.h deklarována  
  
 Import knihovny: VSPerf.lib  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje ResumeProfile funkce. Příklad předpokládá, že volání metody SuspendProfile nebyly provedeny stejným vlákno nebo proces identifikovaný [PROFILE_CURRENTID](../profiling/profile-currentid.md).  
  
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
 [Referenční dokumentace rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)