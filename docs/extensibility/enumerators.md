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
ms.openlocfilehash: 37f469ecc0ae097592a128b30a6a6f189d58d94b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62863951"
---
# <a name="enumerators"></a>Enumerátory
Tato část uvádí výčet datových typů v rozhraní API modulu Plug-in zdroje ovládacího prvku, které musíte znát plug-in správy zdrojových kódů.

## <a name="in-this-section"></a>V tomto oddílu
- [Příkaz kódu](../extensibility/command-code-enumerator.md) vytvoří výčet možností pro [sccgetcommandoptions –](../extensibility/sccgetcommandoptions-function.md) a [sccpopulatelist –](../extensibility/sccpopulatelist-function.md) funkce.

- [Zpráva](../extensibility/message-enumerator.md) vytvoří výčet příznaky použité pro tiskové zpětné volání, [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).

- [Soubor stavový kód](../extensibility/file-status-code-enumerator.md) obsahuje s názvem konstantní hodnoty, které určují stav souboru pod správou zdrojových kódů.

- [Adresář stavový kód](../extensibility/directory-status-code-enumerator.md) obsahuje s názvem konstantní hodnoty, které určují stav adresáře pod správou zdrojových kódů.

## <a name="related-sections"></a>Související oddíly
- [Vytvoření modulu plug-in správy zdrojového kódu](../extensibility/internals/creating-a-source-control-plug-in.md) definuje zdrojový ovládací prvek modulu Plug-in SDK a popisuje zahrnuté prostředky.

- [Sccgetcommandoptions –](../extensibility/sccgetcommandoptions-function.md) vyzve uživatele k rozšířené možnosti pro daný příkaz.

- [Sccpopulatelist –](../extensibility/sccpopulatelist-function.md) zkontroluje seznam souborů pro jejich aktuální stav. Kromě toho používá `pfnPopulate` funkce oznámit volajícímu, soubor neodpovídá kritériím pro `nCommand`.

- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) popisuje funkce zpětného volání, který používá [sccopenproject –](../extensibility/sccopenproject-function.md) pro zobrazení zpráv ze správy zdrojového kódu modulu plug-in pomocí integrovaného vývojového prostředí.

- [Moduly plug-in správy zdrojového](../extensibility/source-control-plug-ins.md) obsahuje úplný seznam všech prvků v rozhraní API modulu Plug-in zdroje ovládacího prvku.