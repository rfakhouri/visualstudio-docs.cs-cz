---
title: Vstextview – objekt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab54fce0271438f89ec66b4fc5d8db1ebe21634f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721417"
---
# <a name="vstextview-object"></a>Vstextview – objekt
Zobrazení textu je okno, které umožňuje uživatelům zobrazit a upravit text v kódu Unicode textové vyrovnávací paměti. Zobrazení je v podstatě, co většina uživatelů označujeme jako editor. Protože zobrazení je oddělen od vyrovnávací paměti různé vrstvy text (zalamování řádků, osnovy textu a tak dále), nemusí být přesné reprezentace textu ve vyrovnávací paměti zobrazení. Další informace o zobrazení textu, naleznete v tématu [přístup k zobrazení text pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)

 V následující tabulce jsou uvedeny rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.

|Rozhraní|Popis|
|---------------|-----------------|
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Povolí vytváření složených akce (to znamená, akce, které jsou seskupeny do jednoho zpět/znovu jednotka).|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|Poskytuje základní metody pro správu a přístup k zobrazení. `IVsTextView` není zřetězený bezpečné.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Vytváří a spravuje podokno okna.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|Komunikuje s vrstvami text.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|Provádí operace pro zobrazení z jiného vlákna.|

## <a name="see-also"></a>Viz také:
- [Úpravy obrázků](https://www.microsoft.com/download/details.aspx?id=55984)
- [Vstextbuffer – objekt](../extensibility/vstextbuffer-object.md)
- [Přístup k zobrazení text pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)