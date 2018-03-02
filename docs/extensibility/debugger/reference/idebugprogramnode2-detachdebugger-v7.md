---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fdf4875c30bebaeed925af57c0d80910f8fcbf21
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> ZASTARALÉ. NEPOUŽÍVEJTE.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>Návratová hodnota

Implementace musí vracet vždycky `E_NOTIMPL`.

## <a name="remarks"></a>Poznámky

> [!WARNING]
> Od verze sady Visual Studio 2005, tato metoda se již nepoužívá a musí vracet vždycky `E_NOTIMPL`.

Tato metoda je volána, když se neočekávaně ukončí ladicího programu. Když tato metoda je volána, DE by mělo být obnoveno program, jakoby z něho odpojený od uživatele. Žádné další události ladění by měly být odeslány. Program musí být ve stavu, kdy je připojitelné z jiné instance systému ladicího programu.

## <a name="see-also"></a>Viz také

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)