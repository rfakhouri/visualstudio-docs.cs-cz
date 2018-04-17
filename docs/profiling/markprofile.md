---
title: MarkProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 113f71d7bf5be7953c4873725086f03905a21c54
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="markprofile"></a>MarkProfile
`MarkProfile` Metoda vloží značku profil v souboru .vsp. Profilace pro přístup z více vláken obsahující `MarkProfile` funkce musí být ON pro značku, která má být vložen.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>Parametry  
 `lMarker`  
  
 Značky pro vložení. Značky musí být větší než nebo rovno 0 (nula).  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch či neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Vrácená hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametr je menší než nebo rovna 0. Tyto hodnoty jsou vyhrazené. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_MODE_NEVER|Profilování režimu byl nastaven na nikdy, při volání funkce. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_MODE_OFF|Profilování režimu byl nastaven na hodnotu OFF, při volání funkce. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_NO_SUPPORT|Nepodporuje označit v tomto kontextu. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_OUTOFMEMORY|Paměť nebyl k dispozici k zaznamenání události. Značky a komentáře nejsou popsané.|  
|MARK_TEXTTOOLONG|Řetězec překračuje maximální povolenou délku 256 znaků. Řetězec komentáře zkrácen a značky a komentáře se zaznamenávají.|  
|MARK_OK|MARK_OK je vrácen do indikuje úspěšné provedení.|  
  
## <a name="remarks"></a>Poznámky  
 Hodnota značky je vložen do souboru .vsp při každém spuštění kódu pokud je profilovaný vlákno obsahující MarkProfile funkce. MarkProfile můžete volat vícekrát.  
  
 Profil značky jsou globální v oboru. Například profil značka vložen do jedno vlákno slouží k označení počáteční nebo koncové segmentu dat v jakékoli vlákno v souboru .vsp.  
  
 Profilování stavu podprocesu, který obsahuje funkci profilu značky musí být v značky a komentáře vložit příkaz Označit nebo s funkcí rozhraní API (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile).  
  
> [!IMPORTANT]
>  Metoda MarkProfile musí být použit s pouze profilace instrumentace.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
 Hlavičky: V VSPerf.h deklarována  
  
 Import knihovny: VSPerf.lib  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje MarkProfile funkce.  
  
```  
void ExerciseMarkProfile()  
{  
    // Declare and initialize variables to pass to   
    // MarkProfile.  The values of these parameters   
    // are assigned based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variables are assigned arbitrary values.  
    int markId = 03;  
  
    // Declare enumeration to hold return value of   
    // call to MarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    markResult = MarkProfile(markId);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("MarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)