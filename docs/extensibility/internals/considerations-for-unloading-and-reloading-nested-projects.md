---
title: "Důležité informace pro uvolnění a načíst vnořený projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fd45ebf8be2732cded5c84f18338f104b76840cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Důležité informace pro uvolnění a překladní vnořené projekty
Při implementaci projektu vnořené typy, musíte provést další kroky, když jste a opětovném načtení projektů. Oznámit správně naslouchací procesy pro řešení události, musíte správně zvýšit `OnBeforeUnloadProject` a `OnAfterLoadProject` události.  
  
 Jedním z důvodů musíte zvýšit tyto události tímto způsobem je, že nechcete, aby zdrojového kódu (SCC) k odstranění položek ze serveru a poté je přidejte jako nové, pokud je `Get` operaci provést z SCC. V takovém případě nový soubor by být načten mimo SCC a máte a opětovném načtení všechny soubory v případě, že se liší. Volání SCC `ReloadItem`. Implementace tohoto volání je odstraňte projekt a znovu jej znovu vytvořit implementací `IVsFireSolutionEvents` volat `OnBeforeUnloadProject` a `OnAfterLoadProject`. Při provádění této implementaci SCC je informován, že projekt byl dočasně odstraněn a znovu přidat. Proto SCC nefunguje na projekt jako kdyby byl projekt ve skutečnosti odstraněn ze serveru a znovu přidat.  
  
## <a name="reloading-projects"></a>Opětovném načtení projektů  
 Pro podporu opětovném načtení projektů vnořené, můžete implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> metoda. V implementaci `ReloadItem`, zavřete vnořené projekty a potom je znovu vytvořit.  
  
 Většinou když je znovu načíst projekt, rozhraní IDE vyvolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> a `M:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject(Microsoft.VisualStudio.Shell.Interop.IVsHierarchy,Microsoft.VisualStudio.Shell.Interop.IVsHierarchy)` události. Pro vnořené projekty, které se odstraní a znovu, ale nadřazený projekt zahájí se proces, není rozhraní IDE. Protože nadřazený projekt nevyvolá řešení události a rozhraní IDE nemá žádné informace o inicializaci procesu, nejsou vyvolány události.  
  
 Ke zpracování tohoto procesu volání nadřazený projekt `QueryInterface` na <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> rozhraní vypnout <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> rozhraní. `IVsFireSolutionEvents`obsahuje funkce, které informují IDE pro vyvolání `OnBeforeUnloadProject` události uvolnění vnořený projekt a poté zvýšit `OnAfterLoadProject` událost, která má stejnou projekt znovu načíst.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 [Vnoření projektů](../../extensibility/internals/nesting-projects.md)