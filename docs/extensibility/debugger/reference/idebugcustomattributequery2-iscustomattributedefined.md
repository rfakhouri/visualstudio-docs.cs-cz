---
title: IDebugCustomAttributeQuery2::IsCustomAttributeDefined | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
ms.assetid: 5c07cc52-6d2d-42df-9d76-9f1f769641db
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0e2ecd70eeeddb4b61d8ed8d307bd579c68ef519
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335829"
---
# <a name="idebugcustomattributequery2iscustomattributedefined"></a>IDebugCustomAttributeQuery2::IsCustomAttributeDefined
Určuje, zda existuje vlastní atribut podle názvu.

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

## <a name="parameters"></a>Parametry
`pszCustomAttributeName`\
[in] Řetězec obsahující název vlastního atributu k vyhledání.

## <a name="return-value"></a>Návratová hodnota
 Vrátí hodnotu S_OK, pokud je vlastní atribut je definován v tomto poli, jinak vrátí S_FALSE.

## <a name="remarks"></a>Poznámky
 Chcete-li získat atribut bajtů spojené s vlastní atribut, zavolejte [getcustomattributebyname –](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)