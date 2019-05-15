---
title: IDebugAlias::GetICorDebugValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5068d687b80da5c75fdef305028c9b5c3d8e56ed
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615171"
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