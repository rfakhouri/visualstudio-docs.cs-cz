---
title: Důležité informace pro uvolnění a opětovné načtení vnořených projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a45cf72f09ddf4e5ac1d68b59c2b13e64982744
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335543"
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Důležité informace pro uvolnění a opětovné načtení vnořených projektů

Při implementaci typy vnořených projektů, je nutné provést další kroky při odebrat a znovu načíst projekty. Pokud chcete informovat správně naslouchacích procesů událostí řešení, musíte správně zvýšit `OnBeforeUnloadProject` a `OnAfterLoadProject` události.

Jedním z důvodů pro vyvolání těchto událostí je pro správu zdrojového kódu (SCC). Nechcete SCC k odstranění položek ze serveru a potom je přidat zpět jako *nové* dojde `Get` zamezil operacím SCC. V takovém případě by mimo SCC načíst nový soubor. Je třeba odebrat a znovu načíst všechny soubory v případě, že charakteristik.

Zdrojový kód ovládacího prvku volá `ReloadItem`. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> rozhraní volat `OnBeforeUnloadProject` a `OnAfterLoadProject` odstraňte projekt a znovu ji vytvořit. Při implementaci rozhraní tímto způsobem SCC je informován, že projekt dočasně odstranila a znovu přidat. Proto SCC nepracuje v projektu jako kdyby byl projekt *skutečně* odstranit a znovu přidat.

## <a name="reload-projects"></a>Znovu načte projekty

Probíhá opětovné načtení vnořených projektů účelem je implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> metoda. Ve vaší implementaci `ReloadItem`, zavřete vnořených projektů a pak je znovu vytvořit.

Obvykle po opětovném načtení nástroje projekt rozhraní IDE vyvolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> události. Pro vnořené projekty, které se odstraní a znovu načten, ale nadřazený projekt zahájí proces, není rozhraní IDE. Protože nadřazený projekt nebude vyvolat události řešení a integrovaného vývojového prostředí nemá žádné informace o inicializaci procesu, události nejsou započteny.

Pro zpracování tohoto procesu, volání nadřazený projekt `QueryInterface` na <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> rozhraní. `IVsFireSolutionEvents` obsahuje funkce, které sdělení rozhraní IDE, aby se vyvolala `OnBeforeUnloadProject` události uvolněte vnořený projekt a poté `OnAfterLoadProject` na stejný projekt znovu načíst události.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Vnoření projektů](../../extensibility/internals/nesting-projects.md)