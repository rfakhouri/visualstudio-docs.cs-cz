---
title: Vstextbuffer – objekt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2a324db2226056fd3f41180055600671a8979a67
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66312791"
---
# <a name="vstextbuffer-object"></a>Vstextbuffer – objekt
Objekt vyrovnávací paměti textu představuje datový proud text v kódu Unicode, který je obvykle přidružen soubor. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt lze použít mimo kontext základní editor, tj. průvodce.

 V následující tabulce jsou uvedeny rozhraní `VSTextBuffer`.

|Metoda|Popis|
|------------|-----------------|
|[IOleCommandTarget](/windows/desktop/api/docobj/nn-docobj-iolecommandtarget)|Standardní rozhraní OLE. Používá se pro zpracování ve vyrovnávací paměti zpět/znovu.|
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Standardní rozhraní OLE.|
|[IPersistStream](/windows/desktop/api/objidl/nn-objidl-ipersiststream)|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytvořit sloučeniny akce (to znamená, akce, které jsou seskupeny do jednoho zpět/znovu jednotka).|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Povolí trvalost dat dokumentu spravuje vyrovnávací paměti textu.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Použitá k vyhledání vyrovnávací paměti.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Umožňuje číst a zapisovat možnosti použití dvojrozměrné souřadnice. Dědí z `IVsTextBuffer`.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Umožňuje číst a zapisovat možnosti pomocí souřadnic jednorozměrné. Dědí z `IVsTextBuffer`.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje možnost rychlého, orientovaný na stream, sekvenční přístup k textu ve vyrovnávací paměti.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecnou kolekci vlastností. Nejdůležitější vlastnost je název nebo moniker vyrovnávací paměti. Náhodná data můžete ukládat do vyrovnávací paměti s tímto rozhraním vytvořením identifikátor GUID a jeho použití jako klíč.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Podporuje spojovací body události.|

## <a name="remarks"></a>Poznámky
 `VSTextBuffer` Je obvykle zjištěných aplikací `QueryInterface` volat `IVsTextBuffer`. Další informace najdete v tématu [textovou vyrovnávací paměť](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>
- [Úpravy obrázků](https://www.microsoft.com/download/details.aspx?id=55984)