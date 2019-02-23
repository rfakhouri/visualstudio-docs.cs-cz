---
title: IDebugMethodField::IsCustomAttributeDefined | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugMethodField::IsCustomAttributeDefined method
ms.assetid: 1b5d95a8-cc87-4acb-9e6a-3928f3632b7c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 08534abc468ac358d7c5eeba25129d9752f84e5a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717085"
---
# <a name="idebugmethodfieldiscustomattributedefined"></a>IDebugMethodField::IsCustomAttributeDefined
Určuje, zda konkrétní vlastního atributu je definována.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsCustomAttributeDefined( 
   LPCOLESTR pszCustomAttributeName
);
```

```csharp
int IsCustomAttributeDefined(
   [In] string pszCustomAttributeName
);
```

#### <a name="parameters"></a>Parametry
 `pszCustomAttributeName`

 [in] Řetězec obsahující název vlastního atributu k vyhledání.

## <a name="return-value"></a>Návratová hodnota
 Vrátí že hodnotu S_OK Pokud vlastního atributu je definována na tuto metodu, v opačném případě vrátí S_FALSE.

## <a name="see-also"></a>Viz také
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)