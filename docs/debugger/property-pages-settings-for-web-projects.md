---
title: "Nastavení stránek vlastností pro webové projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4e58541c5ab0c7a38773740343349880aa5297e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="property-pages-settings-for-web-projects"></a>Nastavení stránek vlastností pro webové projekty
Můžete změnit nastavení vlastností pro konfiguraci ladění webu v **stránky vlastností** dialogové okno, jak je popsáno v [konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md). Následující tabulky popisují kde najít nastavení souvisejících s ladicí program v **stránky vlastností** dialogové okno.  
  
### <a name="configuration-properties-folder-start-options-category"></a>Konfigurace vlastností složky (možnosti spuštění kategorie)  
  
|**Nastavení**|**Popis**|  
|-----------------|---------------------|  
|**Zahájení**|Záhlaví, že možnosti skupiny vztahuje k spuštění aplikace.|  
|**Na aktuální stránce**|Určuje aktuální stránku jako výchozí bod pro ladění.|  
|**Konkrétní stránky:**|Určuje webové stránky, kde chcete začít ladění.|  
|**Spuštění externího programu:**|Určuje příkaz pro spuštění programu, že který chcete ladit.|  
|**Argumenty příkazového řádku:**|Určuje argumenty pro příkaz uveden výše.|  
|**Pracovní adresář:**|Určuje pracovní adresář programu laděné. V [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], pracovní adresář je adresář je aplikace spuštěna z \bin\debug ve výchozím nastavení.|  
|**Počáteční adresa URL**|Určuje umístění, které chcete ladit webové aplikace.|  
|**Nemáte otevřete stránku. Počkejte na žádost z externí aplikace**|Říká čekání na žádost z externí aplikace. Tato možnost se nespustí, Internet Explorer nebo jiné aplikace. Připraví pouze pro ladění při volání aplikací.|  
|**Server**|Záhlaví, že možnosti skupiny vztahuje na server, který se má použít.|  
|**Použít výchozí webový server**|Říká použít výchozí webový server.|  
|**Použít vlastní server**|Umožňuje zadat základní adresu URL pro použití jako server.|  
|**Ladicí programy**|Záhlaví, že možnosti skupiny související s typ ladění provést.|  
|**ASP.NET – ladění**|Povolí ladění na serveru stránek napsané pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] platformu pro vývoj. Musíte zadat adresu URL v **spustit adresu URL**.|  
|**Ladění nativního kódu**|Umožňuje ladění volání do nativního kódu (nespravovaný) Win32 ze spravované aplikace.|  
|**Ladění SQL serveru**|Umožňuje ladění objektů databáze systému SQL Server.|  
|**Ladění aplikací Silverlight**|Umožňuje ladění komponent technologie Silverlight.|  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)