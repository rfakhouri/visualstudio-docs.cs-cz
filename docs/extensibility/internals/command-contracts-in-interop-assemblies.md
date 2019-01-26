---
title: Příkaz smluv ve spolupracujícím sestavení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9daadac56fd74fe78cc5606f94927d1057496dd1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949932"
---
# <a name="command-contracts-in-interop-assemblies"></a>Kontrakty příkazů ve spolupracujícím sestavení
Základní kontrakt pro zpracování příkazů pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní je, že prostředí volá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody k určení, zda příkaz je podporován, a pokud je podporována, chcete-li zjistit jeho stav a text. Potom volá prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody k provedení příkazu.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Metoda se zpracovává stejně jako u všech příkazů. Další komunikace, v případě potřeby (například v rozevíracích seznamech), se spravuje pomocí volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metodu s příslušnými parametry. Výklad tyto parametry závisí na zadaný příkaz.  
  
 Pokud cíl příkazu vrátí hodnoty v výstupní parametr, je vždy volající zodpovědná za uvolnění všechny prostředky, které kdyby byly přiděleny. Protože je tento parametr hodnotu typu variant, vymazání varianty uvolní prostředky.  
  
 V případech, kdy příkazy musí pracovat v okně hierarchie a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní musí být použita. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní má stejný vztah s podobné metody: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>.  
  
## <a name="see-also"></a>Viz také:  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Implementace příkazu](../../extensibility/internals/command-implementation.md)