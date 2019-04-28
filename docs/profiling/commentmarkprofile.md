---
title: CommentMarkProfile | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CommentMarkProfile
- CommentMarkProfileA
ms.assetid: 33ccff45-c33a-4672-b41f-5b317b848cd1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 897ff07f78301553812f6855f3aa4bdb556a650e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440195"
---
# <a name="commentmarkprofile"></a>CommentMarkProfile
`CommentMarkProfile` Funkce vloží značku číselné a textový řetězec v. *Vsp* souboru. Pro značky a komentáře, které má být vložen, profilování pro vlákna, které obsahuje `CommentMarkProfile` funkce musí být dále.

## <a name="syntax"></a>Syntaxe

```cpp
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkProfile(
                                   long lMarker,
                                   LPCTSTR szComment);
```

#### <a name="parameters"></a>Parametry
 `lMarker`

 Číselné značky pro vložení. Značky musí být větší než nebo rovna 0 (nula).

 `szComment`

 Ukazatel na textový řetězec pro vložení. Řetězec musí být kratší než 256 znaků včetně ukončovacího znaku NULL.

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
 Profilace stav podprocesu, který obsahuje funkci profilu značky musí být na při značky a komentáře vložení pomocí příkazu nástroje VSInstr značky nebo s využitím functions (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile).

 Profil značky jsou globální v oboru. Například profil značky vložení v jednom vlákně slouží k označení začátku nebo konci segmentu dat v jakékoli vlákno v. *vsp* souboru.

> [!IMPORTANT]
> Metoda CommentMarkProfile jde použít jenom s instrumentací.

## <a name="net-framework-equivalent"></a>Ekvivalent .NET framework
 Microsoft.VisualStudio.Profiler.dll

## <a name="function-information"></a>Informace o funkci

|||
|-|-|
|**Header**|Zahrnout VSPerf.h|
|**Knihovna**|Použití VSPerf.lib|
|**Unicode**|Implementováno jako `CommentMarkProfileW` (Unicode) a `CommentMarkProfileA` (ANSI).|

## <a name="example"></a>Příklad
 Následující kód znázorňuje volání funkce CommentMarkProfile. V příkladu se předpokládá použití maker řetězec Win32 a Unicode kompilátoru nastavení k určení, zda kód volá [!INCLUDE[vcpransi](../profiling/includes/vcpransi_md.md)] volání funkce.

```cpp
void ExerciseCommentMarkProfile()
{
    // Declare and initalize variables to pass to
    // CommentMarkProfile.  The values of these
    // parameters are assigned based on the needs
    // of the code; and for the sake of simplicity
    // in this example, the variables are assigned
    // arbitrary values.
    long markId = 01;
    TCHAR * markText = TEXT("Exercising CommentMarkProfile...");

    // Variables used to print output.
    HRESULT hResult;
    TCHAR tchBuffer[256];

    // Declare MarkOperationResult Enumerator.
    // Holds return value from call to CommentMarkProfile.
    PROFILE_COMMAND_STATUS markResult;

    markResult = CommentMarkProfile(
        markId,
        markText);

    // Format and print result.
    LPCTSTR pszFormat = TEXT("%s %d.\0");
    TCHAR* pszTxt = TEXT("CommentMarkProfile returned");
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,
        pszTxt, markResult);

#ifdef DEBUG
    OutputDebugString(tchBuffer);
#endif
}
```

## <a name="see-also"></a>Viz také:
- [Visual Studio profiler API reference (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)