---
title: "Výčty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0b9f71c83d70dc6daca7a3906b784d6babf8dea7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="enumerators"></a>Výčty
Tato část uvádí enumerátor datových typů v rozhraní API Plug-in ovládací prvek zdroje, musíte znát modulu plug-in zdrojového kódu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Příkaz kódu](../extensibility/command-code-enumerator.md)  
 Vytvoří výčet možností pro [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) a [SccPopulateList](../extensibility/sccpopulatelist-function.md) funkce.  
  
 [Zpráva](../extensibility/message-enumerator.md)  
 Vytvoří výčet příznaků používá pro tiskové zpětné volání, [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Soubor stavový kód](../extensibility/file-status-code-enumerator.md)  
 Obsahuje pojmenované konstantní hodnoty, které určují stav soubor ve správě zdrojového kódu.  
  
 [Directory stavový kód](../extensibility/directory-status-code-enumerator.md)  
 Obsahuje pojmenované konstantní hodnoty, které určují stav adresáře v rámci správy zdrojového kódu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definuje sadu SDK Plug-in Zdroj ovládacího prvku a popisuje zahrnuté prostředky.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 Vyzve uživatele k rozšířené možnosti pro daný příkaz.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Prozkoumá seznam souborů pro jejich aktuální stav. Kromě toho používá `pfnPopulate` funkce, které oznámí souboru neodpovídá kritériím pro volající `nCommand`.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Popisuje funkce zpětného volání, který je používán [SccOpenProject](../extensibility/sccopenproject-function.md) pro zobrazení zpráv ze zdrojového kódu modulu plug-in pomocí rozhraní IDE.  
  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech elementů v rozhraní API ovládacího prvku Plug-in zdroje.