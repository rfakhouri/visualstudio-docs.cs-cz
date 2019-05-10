---
title: IEnumDebugReferenceInfo2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28e10da879427f885e0af0109e3a701e4fcb44ec
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223247"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
Vytvoří výčet toto rozhraní [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugReferenceInfo2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní jako součást jeho podporu pro odkazy na objekty v paměti. Toto rozhraní musí být implementované jenom v případě, že jsou podporovány odkazy.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Visual Studio volání [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) získat toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugReferenceInfo2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|Načte zadaný počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|Vynechá zadaný počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v pořadí výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|Získá počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v enumerátor.|

## <a name="remarks"></a>Poznámky
 Odkaz je v podstatě typu a adresu, že vlastnost je název, typ a adresu. Odkaz se uchovávají jako objekt uvedené existuje v paměti. Zobrazit [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) další podrobnosti.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)