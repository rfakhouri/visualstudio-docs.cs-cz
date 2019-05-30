---
title: IDebugDocumentText2::GetSize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7f382b1d27a83e4493431ac8e6cca3d6aef9dd72
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337380"
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
Získá velikost textu na této pozici v dokumentu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetSize( 
   ULONG* pcNumLines,
   ULONG* pcNumChars
);
```

```csharp
int GetSize( 
   ref uint pcNumLines,
   ref uint pcNumChars
);
```

## <a name="parameters"></a>Parametry
`pcNumLines`\
[out] Vrátí počet řádků textu.

`pcNumChars`\
[out] Vrátí počet znaků textu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky

 [C++ pouze] Pokud konkrétní hodnoty není žádoucí, předejte hodnotu NULL pro parametr.

 [C# pouze] Je třeba zadat oba parametry.

## <a name="see-also"></a>Viz také:
- [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)