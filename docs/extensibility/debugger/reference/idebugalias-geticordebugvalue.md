---
title: IDebugAlias::GetICorDebugValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 50fb7800c4446e7d13334957ee9f5f6534f254bf
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66338215"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
Načte rozhraní spravovaného kódu, které představuje hodnotu přidruženou k tento alias.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

## <a name="parameters"></a>Parametry
`ppUnk`\
[out] `IUnknown` rozhraní, které představuje hodnotu přidruženou k tento alias. Toto rozhraní je možné zadávat dotazy pro `ICorDebugValue` rozhraní.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tento postup se vztahuje jenom na spravované hodnoty ( `ICorDebugValue` je k dispozici v rozhraní [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] a je definován v [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] sady SDK v souboru cordebug.idl).

## <a name="see-also"></a>Viz také:
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)