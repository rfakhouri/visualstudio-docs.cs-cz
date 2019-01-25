---
title: Izolované prostředí parametry vstupních bodů (C++) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Shell [Visual Studio], isolated mode%2C Start entry point
- Visual Studio shell, isolated mode%2C Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 313632661c3f73fdbd0f23616a068913c77508f8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54804864"
---
# <a name="isolated-shell-entry-point-parameters-c"></a>Parametry vstupních bodů izolovaného prostředí (C++)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při spuštění aplikace založené na prostředí Visual Studio, které volá vstupní bod spuštění z prostředí sady Visual Studio. Tato nastavení lze přepsat při volání funkce vstupní bod spuštění prostředí. Popis jednotlivých nastavení najdete v tématu [. Soubory Pkgdef](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
- AddinsAllowed  
  
- AllowsDroppedFilesOnMainWindow  
  
- AppName  
  
- CommandLineLogo  
  
- DefaultHomePage  
  
- DefaultProjectsLocation  
  
- DefaultSearchPage  
  
- DefaultUserFilesFolderRoot  
  
- DisableOutputWindow  
  
- HideMiscellaneousFilesByDefault  
  
- HideSolutionConcept  
  
- NewProjDlgInstalledTemplatesHdr  
  
- NewProjDlgSlnTreeNodeTitle  
  
- SolutionFileCreatorIdentifier  
  
- SolutionFileExt  
  
- UserFilesSubFolderName  
  
- UserOptsFileExt  
  
  Visual Studio Shell izolované šablona vytvoří zdrojový soubor *solutionName*.cpp, kde *solutionName* je název řešení pro aplikaci. Tento soubor definuje hlavní vstupní bod pro aplikaci _tWinMain funkce. Tato funkce vyvolá vstupní bod spuštění prostředí.  
  
  Můžete změnit chování aplikace změnou tohoto nastavení při spuštění aplikace.  
  
## <a name="parameters"></a>Parametry  
 Vstupní bod spuštění z prostředí sady Visual Studio definuje pěti parametry. Neměňte první čtyři parametry. Pátý parametr přebírá seznam přepsání nastavení. Vstupní bod spuštění prostředí je volána z hlavní vstupní bod aplikace.  
  
 Vstupní bod spuštění prostředí má následující podpis.  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 Pokud nechcete přepsat nastavení aplikace, ponechte hodnotu nastavení přepište parametr jako ukazatel s hodnotou null.  
  
 K přepsání minimálně jedno nastavení, předejte řetězec znaků Unicode, který obsahuje nastavení přepsání. Řetězec se středníkem oddělený seznam dvojic název hodnota. Každý pár obsahuje název nastavení chcete přepsat, za nímž následuje rovnítko (=), za nímž následuje hodnota, která má použít k nastavení.  
  
> [!NOTE]
>  Nezahrnujte prázdné znaky do řetězce Unicode.  
  
 Pro logickou nastavení následující řetězce představují hodnoty true; všechny ostatní řetězce představují hodnotu false. Tyto řetězce jsou malá a velká písmena.  
  
-   \+  
  
-   1  
  
-   -1  
  
-   on  
  
-   true  
  
-   ano  
  
## <a name="example"></a>Příklad  
 Zakázat doplňky a změnit výchozí umístění projektů aplikace, můžete nastavit poslední parametr "AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp".  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení izolovaného prostředí](../extensibility/customizing-the-isolated-shell.md)   
 [Soubory .Pkgdef](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)
