---
title: "Příkaz kontrakty sestavení vzájemné spolupráce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 901423bfa9b43e2d4eaaa20a225c35e76a0b8790
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="command-contracts-in-interop-assemblies"></a>Příkaz kontrakty spolupráce – sestavení
Základní kontrakt pro zpracování pomocí příkazů <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní je, že prostředí volá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda určit, zda příkaz se podporuje, a pokud ji podporuje, a určit její stav a text. Potom volání prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda provedení příkazu.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Metoda se zpracovává stejně jako u všech příkazů. Další komunikace, pokud je to nutné (například v rozevíracích seznamech) spravuje volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda s příslušnými parametry. Výklad tyto parametry závisí na zadaný příkaz.  
  
 Pokud příkaz cíl vrací hodnoty v výstupní parametr, volající zodpovídá vždy pro všechny prostředky, které přidělených uvolnění. Protože je tento parametr hodnotu typu variant, vymazání varianta uvolní prostředky.  
  
 V případech, kdy musí fungovat příkazů v okně hierarchie a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní musí být použita. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní má podobné kontrakt s podobné metody: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Směrování příkazů v VSPackages](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Implementace](../../extensibility/internals/command-implementation.md)