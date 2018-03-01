---
title: "Nastavení projektu VC ++, projekty a řešení, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.VCBuild
helpviewer_keywords:
- builds [Visual Studio], logs
- build process [C++]
- files [Visual Studio], built by C/C++ compiler
- file extensions, built by C or C++ compiler
- cl.exe compiler, file extensions
- extensions, files built by C or C++ compiler
- BuildLog.htm
ms.assetid: 56420efd-6a95-464e-b890-e2b38c48d66a
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f24c1cd65d4669f326f866fbc04160d32daa4a1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vc-project-settings-projects-and-solutions-options-dialog-box"></a>Nastavení projektu VC++, projekty a řešení, dialogové okno Možnosti
Toto dialogové okno umožňuje definovat [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] sestavení a nastavení související s protokolování, výkon a podporuje typy souborů projektu.  
  
### <a name="to-access-this-dialog-box"></a>Pro přístup k tohoto dialogového okna  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  Vyberte **projekty a řešení**a potom vyberte **nastavení projektu VC ++**.  
 
## <a name="build-logging"></a>Sestavení protokolování  
 **Ano**  
  Zapne generování souboru protokolu sestavení. Tato možnost generuje BuildLog.htm, které lze nalézt v adresáři zprostředkující soubory projektu. Každý nový sestavení přepíše předchozí BuildLog.htm soubor.  
  
 **Ne**  
  Generování souboru protokolu sestavení vypne.  

## <a name="show-environment-in-log"></a>Zobrazit prostředí v protokolu  
 **Ano**  
 Seznam proměnných v souboru protokolu sestavení. Tato možnost určuje, že odezvu všech proměnných prostředí během sestavení z [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projekty do souboru protokolu sestavení.  
  
 **Ne**  
 Proměnné prostředí vylučte ze souboru protokolu sestavení.  

## <a name="build-timing"></a>Sestavení časování  
 **Ano**  
  Zapne časování sestavení. Pokud vyberete, je čas potřebný pro na dokončení sestavení publikované ve výstupním okně. Další informace najdete v tématu [výstup – okno](../../ide/reference/output-window.md).  
  
 **Ne**  
 Vypne časování sestavení.  
   
## <a name="maximum-concurrent-c-compilations"></a>Maximální souběžných kompilace C++  
  Určuje maximální počet jader procesoru, který má používat pro paralelní kompilace C++.  
  
## <a name="extensions-to-include"></a>Rozšíření zahrnout  
  Určuje přípony názvů souborů, které můžete přenést do projektu.  

## <a name="extensions-to-hide"></a>Rozšíření skrýt  
  Určuje přípony názvů souborů, které se nezobrazí v **Průzkumníku řešení** při **zobrazit všechny soubory** je povoleno.  

 ## <a name="build-customization-search-path"></a>Vytvořit vlastní nastavení – cesta hledání  
  Určuje seznam adresářů, které obsahují .rules soubory, které vám pomohou definovat pravidla sestavení pro projekty.  

# <a name="solution-explorer-mode"></a>Režim Průzkumník řešení  
 **Zobrazit pouze soubory v projektu**  
  Nakonfiguruje **Průzkumníku řešení** můžete zobrazit jenom soubory v projektu.  
  
 **Zobrazit všechny soubory**  
  Nakonfiguruje **Průzkumníku řešení** zobrazíte soubory v projektu a souborů na disku ve složce projektu.  

## <a name="enable-project-caching"></a>Povolit ukládání do mezipaměti projektu
**Ano**  
Umožňuje sadě Visual Studio projektu ukládat data do mezipaměti, aby při příštím otevření projektu, je možné načíst data, nikoli znovu je computing z projektu souborů z mezipaměti. Pomocí data uložená v mezipaměti můžete výrazně urychlit čas načítání projektu.   

**Ne**  
Nepoužívejte data uložená v mezipaměti projektu. Analyzovat soubory projektu, načte pokaždé, když na projekt.

## <a name="see-also"></a>Viz také  
 [Sestavení C/C++ programů](/cpp/build/building-c-cpp-programs)   
 [Referenční zdroje k sestavení programu v jazyce C/C++](/cpp/build/reference/c-cpp-building-reference)