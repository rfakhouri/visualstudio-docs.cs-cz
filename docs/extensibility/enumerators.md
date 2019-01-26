---
title: Výčty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e57f11f61a1bcb2372a07e34167ecacd324067c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037795"
---
# <a name="enumerators"></a>Enumerátory
Tato část uvádí výčet datových typů v rozhraní API modulu Plug-in zdroje ovládacího prvku, které musíte znát plug-in správy zdrojových kódů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kód příkazu.](../extensibility/command-code-enumerator.md)  
 Vytvoří výčet možností pro [sccgetcommandoptions –](../extensibility/sccgetcommandoptions-function.md) a [sccpopulatelist –](../extensibility/sccpopulatelist-function.md) funkce.  
  
 [Zpráva](../extensibility/message-enumerator.md)  
 Vytvoří výčet příznaky použité pro tiskové zpětné volání, [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Kód stavu souboru](../extensibility/file-status-code-enumerator.md)  
 Obsahuje s názvem konstantní hodnoty, které určují stav souboru pod správou zdrojových kódů.  
  
 [Adresář stavový kód](../extensibility/directory-status-code-enumerator.md)  
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
  
 [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech prvků v rozhraní API modulu Plug-in zdroje ovládacího prvku.