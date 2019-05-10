---
title: IEnumDebugFrameInfo2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFrameInfo2
helpviewer_keywords:
- IEnumDebugFrameInfo2
ms.assetid: 994e30ad-435a-4f9e-9272-d96d9e01099c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6f1be974dae31d321bdb860188b5693747a2e61b
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225559"
---
# <a name="ienumdebugframeinfo2"></a>IEnumDebugFrameInfo2
Vytvoří výčet toto rozhraní [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugFrameInfo2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní uvést seznam struktur, která popisuje aktuální zásobník volání.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Visual Studio volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) získat toto rozhraní pokaždé, když zarážku, výjimka nebo zastavení dochází v programu, který se právě ladí.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugFrameInfo2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)|Načte zadaný počet [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugframeinfo2-skip.md)|Vynechá zadaný počet [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugframeinfo2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugframeinfo2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)|Získá počet [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury v enumerátor.|

## <a name="remarks"></a>Poznámky
 Visual Studio obdrží toto rozhraní jako první krok zpracovávání zarážky, výjimka nebo uživatelem generovaný pozastavení na program, který se právě ladí. Seznam [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktury představuje aktuální zásobník volání, s aktuálním volání funkce na začátku seznamu a nejstarší funkce volání na konci seznamu. Každý `FRAMEINFO` představuje rámec zásobníku, kontext, ve kterém můžete vyhodnotit výrazy a prohlédli jste si místní proměnné.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)