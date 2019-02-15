---
title: EncUnavailableReason | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- EncUnavailableReason
helpviewer_keywords:
- EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7ccc05c58eafe6f8902b3f8ac09b90dc771a3009
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315685"
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!` Představuje důvody, které **upravit a pokračovat** není k dispozici.

## <a name="syntax"></a>Syntaxe

```cpp
enum tagEncUnavailableReason {
    ENCUN_NONE,
    ENCUN_INTEROP,
    ENCUN_SQLCLR,
    ENCUN_MINIDUMP,
    ENCUN_EMBEDDED,
    ENCUN_ATTACH,
    ENCUN_WIN64
};
typedef enum tagEncUnavailableReason EncUnavailableReason;
```

```csharp
public enum EncUnavailableReason {
    ENCUN_NONE,
    ENCUN_INTEROP,
    ENCUN_SQLCLR,
    ENCUN_MINIDUMP,
    ENCUN_EMBEDDED,
    ENCUN_ATTACH,
    ENCUN_WIN64
};
```

#### <a name="parameters"></a>Parametry
ENCUN_NONE  
Žádné konkrétní důvod, proč upravit a pokračovat není k dispozici.

ENCUN_INTEROP  
Upravit a pokračovat není během volání rozhraní InterOp k dispozici.

ENCUN_SQLCLR  
Upravit a pokračovat není při volání procedury SQL, která používá Common Language Runtime (CLR) k dispozici.

ENCUN_MINIDUMP  
Upravit a pokračovat není při zpracování mini výpis paměti k dispozici.

ENCUN_EMBEDDED  
Při zpracování vloženého kódu, upravit a pokračovat není k dispozici.

ENCUN_ATTACH  
Upravit a pokračovat není k dispozici protože relace byla přiřazena, nespustí, ladicím programem.

ENCUN_WIN64  
Upravit a pokračovat není při zpracování kódu Windows 64-bit k dispozici.

## <a name="remarks"></a>Poznámky
Tento výčet je pro interní použití pouze podle [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]. [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md) a [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md) metod, jak je implementován dodavatelem port. Tento vlastní port byste vždy vrátí `E_NOTIMPL`.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.idl

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)

[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)

[GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)

