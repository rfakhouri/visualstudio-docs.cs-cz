---
title: MarkProfile | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15a53b3423cbda77f0625e6791e96db740636000
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925185"
---
# <a name="markprofile"></a>MarkProfile
`MarkProfile` Metoda vloží značku profilu v. *Vsp* souboru. Profilování pro vlákna obsahující `MarkProfile` funkce musí být ON pro značku má být vložen.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>Parametry  
 `lMarker`  
  
 Značky pro vložení. Značky musí být větší než nebo rovna 0 (nula).  
  
## <a name="property-valuereturn-value"></a>Vlastnost hodnota nebo návratová hodnota  
 Funkce označuje úspěch nebo neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Návratová hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametr je menší než nebo rovna 0. Tyto hodnoty jsou vyhrazené. Nejsou zaznamenána značky a komentáře.|  
|MARK_ERROR_MODE_NEVER|Režimu profilace byla nastavena na nikdy, když byla volána funkce. Nejsou zaznamenána značky a komentáře.|  
|MARK_ERROR_MODE_OFF|Režimu profilace byl nastaven na hodnotu OFF, když byla volána funkce. Nejsou zaznamenána značky a komentáře.|  
|MARK_ERROR_NO_SUPPORT|Bez podpory označení v tomto kontextu. Nejsou zaznamenána značky a komentáře.|  
|MARK_ERROR_OUTOFMEMORY|Paměť není k dispozici k zaznamenání události. Nejsou zaznamenána značky a komentáře.|  
|MARK_TEXTTOOLONG|Řetězec překračuje maximum 256 znaků. Komentář řetězce zkráceny a značky a komentáře se zaznamenávají.|  
|MARK_OK|MARK_OK je vrácena, čímž indikuje úspěšné provedení.|  
  
## <a name="remarks"></a>Poznámky  
 Hodnota značky je vložen do. *vsp* souboru při každém spuštění kódu Pokud vlákno obsahující funkci MarkProfile je právě profilována. MarkProfile můžete volat více než jednou.  
  
 Profil značky jsou globální v oboru. Například profil značky vložení v jednom vlákně slouží k označení začátku nebo konci segmentu dat v jakékoli vlákno v. *vsp* souboru.  
  
 Profilace stav podprocesu, který obsahuje funkci profilu značky musí být na značky a komentáře vložená značka příkaz nebo s funkcí rozhraní API (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile).  
  
> [!IMPORTANT]
>  Metoda MarkProfile by měla sloužit s pouze profilaci instrumentace.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent .NET framework  
 *Microsoft.VisualStudio.Profiler.dll*  
  
## <a name="function-information"></a>Informace o funkci  
 Záhlaví: Deklarované v *VSPerf.h*  
  
 Knihovna importů: *VSPerf.lib*  
  
## <a name="example"></a>Příklad  
 Následující kód znázorňuje MarkProfile funkce.  
  
```cpp  
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
  
## <a name="see-also"></a>Viz také:  
 [Visual Studio profiler API reference (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)