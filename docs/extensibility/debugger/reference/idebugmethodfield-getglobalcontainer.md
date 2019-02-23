---
title: IDebugMethodField::GetGlobalContainer | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::GetGlobalContainer
helpviewer_keywords:
- IDebugMethodField::GetGlobalContainer method
ms.assetid: 041ac5aa-0b80-4310-b9ae-b88f8e7e0e5f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 40bbee4c00425c4f46ccde35b8a8c810e1d7c8e6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717504"
---
# <a name="idebugmethodfieldgetglobalcontainer"></a>IDebugMethodField::GetGlobalContainer
Získá kontejner globální metody.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetGlobalContainer(
   IDebugClassField** ppClass
);
```

```csharp
int GetGlobalContainer(
   out IDebugClassField ppClass
);
```

#### <a name="parameters"></a>Parametry
 `ppClass`

 [out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) představující modul, ve kterém je definována této metody.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vrácený [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objekt představuje celý modul a je umělý objekt, to znamená, samotný modul nemá skutečný třídy, ale lze reprezentovat `IDebugClassField` objektu, povoluje různých elementy modulu je možné vytvořit výčet a zjistit.

## <a name="see-also"></a>Viz také
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)