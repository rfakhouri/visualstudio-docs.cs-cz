---
title: CANSTOP_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CANSTOP_REASON
helpviewer_keywords:
- CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 18861d7aa19281528e9a100f57399451194598a9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66327253"
---
# <a name="canstopreason"></a>CANSTOP_REASON
Umožňuje určit, pokud program můžete zastavit provádění po dosažení určitého bodu v provádění.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_CANSTOP_REASON {
    CANSTOP_ENTRYPOINT = 0x0000,
    CANSTOP_STEPIN     = 0x0001
};
typedef DWORD CANSTOP_REASON;
```

```csharp
public enum enum_CANSTOP_REASON {
    CANSTOP_ENTRYPOINT = 0x0000,
    CANSTOP_STEPIN     = 0x0001
};
```

## <a name="fields"></a>Pole
`CANSTOP_ENTRYPOINT`\
Určuje vstupní bod určený program.

`CANSTOP_STEPIN`\
Určuje vstup do funkce.

## <a name="remarks"></a>Poznámky
Předán jako argument [getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metody pro potvrzení se relace ladění správce (SDM), pokud je v pořádku po dosažení vstupní bod programu nebo po přechodu na funkci nebo metodu.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)
