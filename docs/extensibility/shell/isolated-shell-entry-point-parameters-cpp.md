---
title: "Izolované prostředí vstupní bod parametrů (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], isolated mode, Start entry point
- Visual Studio shell, isolated mode, Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 54b15d849efacb681eb8b4238cd067144bc67342
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="isolated-shell-entry-point-parameters-c"></a>Izolované prostředí vstupní bod parametrů (C++)
Při spuštění aplikace z Visual Studia založený na prostředí, zavolá vstupní bod spuštění z prostředí sady Visual Studio. Následující nastavení může být přepsána ve volání vstupní bod spuštění prostředí. Popis jednotlivých nastaveních najdete v tématu [. Soubory Pkgdef](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
-   AddinsAllowed  
  
-   AllowsDroppedFilesOnMainWindow  
  
-   AppName  
  
-   CommandLineLogo  
  
-   DefaultHomePage  
  
-   DefaultProjectsLocation  
  
-   DefaultSearchPage  
  
-   DefaultUserFilesFolderRoot  
  
-   DisableOutputWindow  
  
-   HideMiscellaneousFilesByDefault  
  
-   HideSolutionConcept  
  
-   NewProjDlgInstalledTemplatesHdr  
  
-   NewProjDlgSlnTreeNodeTitle  
  
-   SolutionFileCreatorIdentifier  
  
-   SolutionFileExt  
  
-   UserFilesSubFolderName  
  
-   UserOptsFileExt  
  
 Visual Studio Shell izolované šablona vytvoří zdrojový soubor *název řešení solutionName*sada, kde *název řešení solutionName* je název řešení pro aplikaci. Tento soubor definuje hlavní vstupní bod pro aplikaci, _tWinMain funkce. Tato funkce vyvolá vstupní bod spuštění prostředí.  
  
 Změna těchto nastavení při spuštění aplikace, můžete změnit chování aplikace.  
  
## <a name="parameters"></a>Parametry  
 Vstupní bod spuštění z prostředí sady Visual Studio definuje pět parametry. Neměňte první čtyři parametry. Pátého parametru přebírá seznam nastavení přepsat. Vstupní bod spuštění prostředí je volána z hlavní vstupní bod aplikace.  
  
 Vstupní bod spuštění prostředí má následující podpis.  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 Pokud nechcete přepsat nastavení aplikace, ponechte hodnotu nastavení přepište parametr jako ukazatel s hodnotou null.  
  
 Pokud chcete přepsat jedno nebo více nastavení, předejte řetězec znaků Unicode, který obsahuje nastavení k přepsání. Řetězec je středníky oddělený seznam dvojic název hodnota. Každý pár obsahuje název nastavení chcete přepsat, a potom rovná se (=), za nímž následuje hodnota, která má použít k nastavení.  
  
> [!NOTE]
>  Nezahrnovat prázdných znaků do řetězců kódování Unicode.  
  
 Pro logickou nastavení následující řetězce reprezentuje hodnotu true; všechny ostatní řetězce představují hodnotu false. Tyto řetězce jsou velká a malá písmena.  
  
-   \+  
  
-   1  
  
-   -1  
  
-   on  
  
-   true  
  
-   Ano  
  
## <a name="example"></a>Příklad  
 Pokud chcete zakázat doplňky a změnit výchozí umístění projekty pro vaši aplikaci, můžete nastavit poslední parametr "AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp".  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení izolované prostředí](customizing-the-isolated-shell.md)   
 [. Pkgdef soubory](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)