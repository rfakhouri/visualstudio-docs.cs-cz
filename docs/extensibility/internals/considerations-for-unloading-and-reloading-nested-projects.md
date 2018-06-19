---
title: Důležité informace pro uvolnění a načíst vnořený projekty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7f22575c4affa6e6a13ea80b32674a3e517202fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127916"
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Důležité informace pro uvolnění a překladní vnořené projekty

Při implementaci projektu vnořené typy, musíte provést další kroky, když jste a opětovném načtení projektů. Oznámit správně naslouchací procesy pro řešení události, musíte správně zvýšit `OnBeforeUnloadProject` a `OnAfterLoadProject` události.

Jedním z důvodů k vyvolání těchto událostí je pro řízení zdrojového kódu (SCC). Nechcete, aby SCC odstranit položky ze serveru a pak je přidejte zpět jako *nové* Pokud dojde `Get` operaci provést z SCC. V takovém případě by mimo SCC načíst nový soubor. Je třeba a opětovném načtení všechny soubory v případě, že jsou různé.

Zdroj ovládacího prvku kód zavolá metodu `ReloadItem`. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> pro volání rozhraní `OnBeforeUnloadProject` a `OnAfterLoadProject` odstraňte projekt a znovu vytvořit. Při implementaci rozhraní tímto způsobem je informován SCC, že projekt byl dočasně odstraněn a znovu přidat. Proto SCC nepracuje na projekt jako kdyby byla projektu *ve skutečnosti* odstraněna a znovu přidat.

## <a name="reloading-projects"></a>Opětovném načtení projektů

Pro podporu opětovném načtení projektů vnořené, můžete implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> metoda. V implementaci `ReloadItem`, zavřete vnořené projekty a potom je znovu vytvořit.

Většinou když je znovu načíst projekt, rozhraní IDE vyvolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> události. Pro vnořené projekty, které jsou odstraněna a znovu, ale nadřazený projekt zahájí se proces, není rozhraní IDE. Protože nadřazený projekt není vyvolávání událostí řešení a rozhraní IDE nemá žádné informace o inicializaci procesu, nejsou vyvolány události.

Ke zpracování tohoto procesu volání nadřazený projekt `QueryInterface` na <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> rozhraní. `IVsFireSolutionEvents` obsahuje funkce, které informují IDE pro vyvolání `OnBeforeUnloadProject` události uvolnění vnořený projekt a poté zvýšit `OnAfterLoadProject` událost, která má stejnou projekt znovu načíst.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Vnoření projektů](../../extensibility/internals/nesting-projects.md)