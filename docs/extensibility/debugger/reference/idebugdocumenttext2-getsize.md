---
title: IDebugDocumentText2::GetSize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9207858bd43809cbc070935ae2f53f354d9d6f9b
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199162"
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