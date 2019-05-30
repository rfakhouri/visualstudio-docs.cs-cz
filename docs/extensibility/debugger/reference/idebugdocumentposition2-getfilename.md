---
title: IDebugDocumentPosition2::GetFileName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2::GetFileName
helpviewer_keywords:
- IDebugDocumentPosition2::GetFileName
ms.assetid: d713635e-088f-465b-b26d-00ac971c9e86
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 478f259d111e19df988c76733d1bb52655adab2c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326531"
---
# <a name="idebugdocumentposition2getfilename"></a>IDebugDocumentPosition2::GetFileName
Získá název souboru zdrojového souboru, který obsahuje umístění dokumentu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetFileName( 
   BSTR* pbstrFileName
);
```

```csharp
int GetFileName( 
   out string pbstrFileName
);
```

## <a name="parameters"></a>Parametry
`pbstrFileName`\
[out] Vrátí název souboru zdrojového souboru.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Zdrojový soubor nemusí mít vždy název souboru (zdrojový soubor neexistuje na disku, například).

## <a name="see-also"></a>Viz také:
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)