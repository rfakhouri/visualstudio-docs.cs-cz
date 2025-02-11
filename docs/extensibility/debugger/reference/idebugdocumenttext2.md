---
title: IDebugDocumentText2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentText2
helpviewer_keywords:
- IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 43716ce3b01464d2937fd75ce90ec5028679ef47
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330647"
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
Toto rozhraní představuje textový dokument.

## <a name="syntax"></a>Syntaxe

```
IDebugDocumentText2 : IDebugDocument2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní, pokud je zdrojový kód, je potřeba zadat v textové podobě. Protože toto je nejčastější případ, pokud se Zavedenými implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní, měl by také implementovat `IDebugDocumentText2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Použití `QueryInterface` metodu k získání tohoto rozhraní ze `IDebugDocument2` rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na `IDebugDocument2` rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|Získá velikost textu na této pozici v dokumentu.|
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|Získá text ze zadaného umístění v dokumentu.|

## <a name="remarks"></a>Poznámky
 Musí také implementovat objekt, který implementuje toto rozhraní <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní, které poskytuje <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní pro [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) objektu.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
- [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)