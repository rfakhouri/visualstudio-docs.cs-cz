---
title: NameProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- NameProfile
- NameProfileA
ms.assetid: 1bb05441-c4ff-4323-9fef-f3924fba4430
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1111ad05df4d9ae74556d940438046aaccad116f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="nameprofile"></a>NameProfile
`NameProfile` Funkce přiřadí řetězec zadaný proces nebo přístup z více vláken.  
  
 Rozhraní API NameProfile je k dispozici pouze pro profilace instrumentace. Rozhraní API NameProfile nepodporuje profilace vzorkování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI NameProfile(  
                                   LPCTSTR pszName,   
                                   PROFILE_CONTROL_LEVEL Level,  
                                   unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszName`  
  
 Název elementu profilování. Název je neplatný (výsledkem návratový NAME_ERROR_INVALID_NAME NameProfileA), pokud:  
  
-   Ukazatel předaný do NameProfileA je hodnoty NULL  
  
-   Řetězec data pszName začíná číslem  
  
-   Řetězec data pszName obsahuje mezery  
  
-   Řetězec data pszName obsahuje některý z následujících znaků:,. ' ~! @# $% ^ & * () = [] {}&#124;\\? / <>  
  
 `Level`  
  
 Informuje o úrovni profilu, které výkon shromažďování dat lze použít. Následující **PROFILE_CONTROL_LEVEL** hodnoty lze použít k označení jednu ze tří úrovní, které výkon lze použít shromažďování dat:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globální nastavení úrovně ovlivňuje všechny procesy a vláken v profilaci spustit.|  
|PROFILE_PROCESSLEVEL|Nastavení úrovně proces ovlivnit všechna vlákna, které jsou součástí určený proces.|  
|PROFILE_THREADLEVEL|Přístup z více vláken profilace nastavení úrovně ovlivňuje zadaný vlákno.|  
  
 `dwId`  
  
 Profilace úrovně identifikátor. Pomocí procesu nebo vlákna identifikátor, který je generováno systémem.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch či neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Vrácená hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|NAME_ERROR_ID_NOEXIST|Profilování zadaného prvku neexistuje.|  
|NAME_ERROR_INVALID_NAME|Název je neplatný.|  
|NAME_ERROR_LEVEL_NOEXIST|Zadaný profil úroveň neexistuje.|  
|NAME_ERROR_NO_SUPPORT|Zadaná operace není podporována.|  
|NAME_ERROR_OUTOFMEMORY|Paměť nebyl k dispozici k zaznamenání události.|  
|NAME_ERROR_REDEFINITION|Název byl již přiřazen k elementu profilu. Název této funkce se ignoruje.|  
|NAME_ERROR_TEXTTRUNCATED|Text názvu překročila maximální 32 znaků včetně znak hodnoty null a byl proto zkrácen.|  
|NAME_OK|Název byl úspěšně zaregistrován.|  
  
## <a name="remarks"></a>Poznámky  
 Každý proces nebo přístup z více vláken lze přiřadit jenom jeden název. Po profilování element s názvem, se ignorují následující volání NameProfile pro daný element.  
  
 Je-li se stejným názvem do různých vláknech nebo procesů, bude sestava obsahovat data z všechny prvky na této úrovni s tímto názvem.  
  
 Pokud zadáte procesu nebo podprocesu, než aktuální, musí se ujistěte, že má být inicializován a spuštění předtím, než použijete název. Metoda NameProfile, jinak selže.  
  
> [!IMPORTANT]
>  Funkce CreateProcess() a rozhraní API CreateThread() může vrátit před vlákno nebo procesu je inicializován.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
  
|||  
|-|-|  
|**Záhlaví**|Zahrnout VSPerf.h|  
|**Knihovna**|Použití VSPerf.lib|  
|**Unicode**|Implementovaná jako `NameProfileW` (Unicode) a `NameProfileA` (ANSI).|  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje volání funkce NameProfile. Příklad předpokládá použití Win32 řetězce makra a nastavení kompilátoru pro ANSI k určení, zda kód zavolá metodu ANSI povolený funkce.  
  
```  
void ExerciseNameProfile()  
{  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Create and initialize variables to pass to   
    // ExerciseNameProfile.  The value of this   
    // parameter is based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variable is assigned an arbitrary value.  
    TCHAR * profileName = TEXT("ExerciseNameProfile");  
  
    // Declare enumeration to hold result of call to   
    // ExerciseNameProfle.  
    PROFILE_COMMAND_STATUS nameResult;  
  
    nameResult =  NameProfile(  
        profileName,  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("NameProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, nameResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)