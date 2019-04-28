---
title: IDebugDocument2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2
helpviewer_keywords:
- IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28334cc7aa0c8a5587a20d6c9dfdee3133d9ea7e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921787"
---
# <a name="idebugdocument2"></a>IDebugDocument2
Toto rozhraní představuje zdrojovém dokumentu.

## <a name="syntax"></a>Syntaxe

```
IDebugDocument2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] obvykle implementuje toto rozhraní. Ladicí stroj (DE) můžete také implementovat toto rozhraní je potřeba zadat zdrojový kód a zdroji neexistuje na disku.  V takových případech by implementovat taky DE [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) a [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) rozhraní, jakož i některé další metody na [ IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) a [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Metody `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, a `IDebugActivateDocumentEvent2` rozhraní vrátit toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugDocument2`.

|Metoda|Popis|
|------------|-----------------|
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|Získá název dokumentu v jednom z několika způsoby.|
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|Získá identifikátor třídy dokumentu.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je implementováno pouze v případě, že je DE poskytuje zdrojový kód. Například při ladění skriptů na stránku HTML, DE poskytuje zdrojový kód je stáhnout nebo dynamicky generované zdroj a jako soubor na disku neexistuje. Při ladění tradiční jazyků, jako je například C++, není nutné implementovat toto rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)
- [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)