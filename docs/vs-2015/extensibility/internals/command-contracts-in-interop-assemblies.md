---
title: Příkaz smluv ve spolupracujícím sestavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 50d48d3a8ff55559cce1c3a40142e31b8eebd85f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68195122"
---
# <a name="command-contracts-in-interop-assemblies"></a>Kontrakty příkazů v definičních sestaveních
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Základní kontrakt pro zpracování příkazů pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní je, že prostředí volá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody k určení, zda příkaz je podporován, a pokud je podporována, chcete-li zjistit jeho stav a text. Potom volá prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metody k provedení příkazu.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Metoda se zpracovává stejně jako u všech příkazů. Další komunikace, v případě potřeby (například v rozevíracích seznamech), se spravuje pomocí volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metodu s příslušnými parametry. Výklad tyto parametry závisí na zadaný příkaz.  
  
 Pokud cíl příkazu vrátí hodnoty v výstupní parametr, je vždy volající zodpovědná za uvolnění všechny prostředky, které kdyby byly přiděleny. Protože je tento parametr hodnotu typu variant, vymazání varianty uvolní prostředky.  
  
 V případech, kdy příkazy musí pracovat v okně hierarchie a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní musí být použita. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní má stejný vztah s podobné metody: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Implementace](../../extensibility/internals/command-implementation.md)
