---
title: IDebugDocument2::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2::GetName
helpviewer_keywords:
- IDebugDocument2::GetName
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 31eddcc07adc181e179c3f3edba669fff85fa565
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66310270"
---
# <a name="idebugdocument2getname"></a>IDebugDocument2::GetName
Získá název dokumentu v jednom z několika způsoby.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName( 
   GETNAME_TYPE gnType,
   BSTR*        pbstrFileName
);
```

```csharp
int GetName( 
   enum_GETNAME_TYPE gnType,
   out string        pbstrFileName
);
```

## <a name="parameters"></a>Parametry
`gnType`\
[in] Hodnota z [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md) výčet, který určuje typ název, který vrátí.

`pbstrFileName`\
[out] Vrátí řetězec obsahující název dokumentu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda může například vrátit název dokumentu, jako název nebo název souboru nebo dokonce i část názvu souboru.

## <a name="see-also"></a>Viz také:
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
- [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)