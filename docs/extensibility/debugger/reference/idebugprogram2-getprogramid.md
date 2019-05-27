---
title: IDebugProgram2::GetProgramId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetProgramId
helpviewer_keywords:
- IDebugProgram2::GetProgramId
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ca86175d34cc1bfd54882adda7e1f7cb464fb22f
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212638"
---
# <a name="idebugprogram2getprogramid"></a>IDebugProgram2::GetProgramId
Získá identifikátor GUID tohoto programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProgramId( 
   GUID* pguidProgramId
);
```

```csharp
int GetProgramId( 
   out Guid pguidProgramId
);
```

## <a name="parameters"></a>Parametry
`pguidProgramId`\
[out] Vrátí `GUID` tohoto programu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Ladicí stroj (DE) musí vrátit identifikátor programu původně předána [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) nebo [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody. Díky tomu identifikace programu v ladicím programu komponenty.

## <a name="see-also"></a>Viz také:
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)