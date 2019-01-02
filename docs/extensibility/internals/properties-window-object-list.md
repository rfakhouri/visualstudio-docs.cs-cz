---
title: Seznam objektů okna Vlastnosti | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e014889613317f773a741b6e43e6f08e5494af5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868716"
---
# <a name="properties-window-object-list"></a>Seznam objektů okna Vlastnosti
V seznamu objektů **vlastnosti** okno je rozevírací seznam, který vám umožní změnit výběr na jiné objekty, které jsou k dispozici v rámci jednoho nebo více vybraných windows. Vyberte jiný objekt z v rámci tohoto seznamu aktivuje volání <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> prostředí informovat, že byla vybrána nový objekt. Informace zobrazené **vlastnosti** okno se pak změní na Zobrazit vlastnosti přidružené k nově vybraného objektu.  
  
## <a name="the-object-list"></a>V seznamu objektů  
 Seznam objektů se skládá ze dvou polí: název objektu (zobrazená tučným písmem) a typ objektu.  
  
 Název objektu zobrazena nalevo od typ objektu tučným písmem je načten z objektu samotného pomocí `Name` vlastnost poskytované <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> rozhraní. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>, jedinou metodou na <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, vrátí <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> pro toto rozhraní coclass. **Vlastnosti** okno používá <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> a získat tak název třídy typu coclass, který se zobrazí jako název objektu v rozevíracím seznamu.  
  
 Pokud objekt nemá `Name` vlastnost názvu se nezobrazí v oblasti název seznamu objektů. Vlastnost názvu můžete přidat do objektu, pokud chcete, aby název zobrazený v seznamu objektů.  
  
 Pokud objekt COM neimplementuje <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, **vlastnosti** okna zobrazuje název rozhraní místo názvu objektu na levé straně seznamu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vlastností](../../extensibility/internals/extending-properties.md)