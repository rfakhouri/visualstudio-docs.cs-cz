---
title: Výčty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4dcc660ba5aacf1b8014e7c4ca15443f2fdf881b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49258496"
---
# <a name="enumerators"></a>Enumerátory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část uvádí výčet datových typů v rozhraní API modulu Plug-in zdroje ovládacího prvku, které musíte znát plug-in správy zdrojových kódů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kód příkazu](../extensibility/command-code-enumerator.md)  
 Vytvoří výčet možností pro [sccgetcommandoptions –](../extensibility/sccgetcommandoptions-function.md) a [sccpopulatelist –](../extensibility/sccpopulatelist-function.md) funkce.  
  
 [Zpráva](../extensibility/message-enumerator.md)  
 Vytvoří výčet příznaky použité pro tiskové zpětné volání, [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Kód stavu souboru](../extensibility/file-status-code-enumerator.md)  
 Obsahuje s názvem konstantní hodnoty, které určují stav souboru pod správou zdrojových kódů.  
  
 [Kód stavu adresáře](../extensibility/directory-status-code-enumerator.md)  
 Obsahuje s názvem konstantní hodnoty, které určují stav adresáře pod správou zdrojových kódů.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření modulu plug-in správy zdrojového kódu](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definuje ovládací prvek modulu Plug-in Source sad SDK a popisuje zahrnuté prostředky.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 Vyzve uživatele k rozšířené možnosti pro daný příkaz.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Zkontroluje seznam souborů pro jejich aktuální stav. Kromě toho používá `pfnPopulate` funkce oznámit volajícímu, soubor neodpovídá kritériím pro `nCommand`.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Popisuje funkce zpětného volání, který používá [sccopenproject –](../extensibility/sccopenproject-function.md) pro zobrazení zpráv ze správy zdrojového kódu modulu plug-in pomocí integrovaného vývojového prostředí.  
  
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech prvků v rozhraní API modulu Plug-in zdroje ovládacího prvku.

