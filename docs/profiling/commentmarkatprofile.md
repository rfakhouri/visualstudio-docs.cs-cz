---
title: CommentMarkAtProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- CommentMarkAtProfile
- CommentMarkAtProfileA
ms.assetid: 04294ca3-bf9c-4c76-86f1-898c2140de27
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1ced0f3e882025e4a6e1bdd940f5aa0d189beb58
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34690972"
---
# <a name="commentmarkatprofile"></a>CommentMarkAtProfile
`CommentMarkAtProfile` Metoda vloží hodnoty časového razítka, číselné značky a komentáře řetězce v. *Vsp* souboru. Hodnota časového razítka slouží k synchronizaci externí události. Značky a komentáře, které má být vložen profilace podprocesu, který obsahuje funkci CommentMarkAtProfile musí být ON.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkAtProfile (  
                                   __int64 dnTimestamp,  
                                   long lMarker,  
                                   LPCTSTR szComment);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dnTimestamp`  
  
 64bitové celé číslo, představující hodnotu časového razítka.  
  
 `lMarker`  
  
 Číselné značky pro vložení. Značky musí být větší než nebo rovno 0 (nula).  
  
 `szComment`  
  
 Ukazatel na textový řetězec k vložení. Řetězec musí být kratší než 256 znaků včetně ukončení hodnotu NULL.  
  
## <a name="property-valuereturn-value"></a>Vlastnost Hodnota/Návratová hodnota  
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
 Profilování stavu podprocesu, který obsahuje funkci profilu značky musí být v značky a komentáře vložit příkaz Označit nebo s funkcí rozhraní API (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile). Profil značky jsou globální v oboru. Například profil značka vložen do jedno vlákno slouží k označení počáteční nebo koncové segmentu dat v jakékoli vlákno v souboru .vsp.  
  
> [!IMPORTANT]
>  CommentMarkAtProfile metody musí být použit s pouze instrumentace.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
  
|||  
|-|-|  
|**Záhlaví**|Zahrnout VSPerf.h|  
|**Knihovna**|Použití VSPerf.lib|  
|**Unicode**|Implementovaný jako CommentMarkAtProfileW (Unicode) a CommentMarkAtProfileA (ANSI).|  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje použití volání CommentMarkAtProfile obecné funkce. Příklad předpokládá použití Win32 řetězce makra a nastavení kompilátoru pro ANSI k určení, zda kód zavolá metodu ANSI povolený funkce.  
  
```cpp  
void ExerciseCommentMarkAtProfile(void)  
{  
    // Declare and initalize variables to pass to   
    // CommentMarkAtProfile.  The values of these   
    // parameters are assigned based on the needs   
    // of the code; and for the sake of simplicity  
    // in this example, the variables are assigned  
    // arbitrary values.  
    int64 timeStamp = 0x1111;  
    long markId = 01;  
    TCHAR * markText = TEXT("Exercising CommentMarkAtProfile...");  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare MarkOperationResult Enumerator.    
    // Holds return value from call to CommentMarkAtProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    markResult = CommentMarkAtProfile(  
        timeStamp,  
        markId,  
        markText);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("CommentMarkAtProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
    pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace jazyka Visual Studio Profiler API (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)