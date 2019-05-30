---
title: IDebugCustomAttribute::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3ed7abc9682d0a9f56c50fe7510ed3f276a6bf5a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315210"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
Získá název vlastního atributu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName( 
   BSTR* bstrName
);
```

```csharp
int GetName(
   out string bstrName
);
```

## <a name="parameters"></a>Parametry
`bstrName`\
[out] Vrátí řetězec obsahující název vlastního atributu.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pojmenované vrácený touto metodou odpovídá názvu třídy, který deklaruje atribut. To může přesně odpovídat názvu vlastní třídy vlastní atribut jako C# umožňuje příponu "Atribut" chcete vyřadit z názvu vlastního atributu při použití v deklaraci.

## <a name="see-also"></a>Viz také:
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)