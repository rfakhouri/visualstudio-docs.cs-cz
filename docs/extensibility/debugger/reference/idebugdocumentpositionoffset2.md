---
title: IDebugDocumentPositionOffset2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3793d54249fca1dc867cfe4072326245a67852cb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333273"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
Představuje pozici ve zdrojovém souboru jako odsazení znaku.

## <a name="syntax"></a>Syntaxe

```
IDebugDocumentPositionOffset2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Implementované integrovaným vývojovým prostředím a spotřebovávány ladicí stroj.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentPositionOffset2`.

|Metoda|Popis|
|------------|-----------------|
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|Načte rozsah pro aktuální pozice v dokumentu.|

## <a name="remarks"></a>Poznámky
 Vrátí stejné informace jako [getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) ale `char` posun od začátku dokumentu. To představuje dokument jako jeho by existovat na disku, to znamená, jednorozměrné pole znaků, namísto řádku a sloupci informace, které se obvykle vrátí.

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)