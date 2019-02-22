---
title: IDebugDocumentContext2::GetSourceRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetSourceRange
helpviewer_keywords:
- IDebugDocumentContext2::GetSourceRange
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 206ed65d4374a6dc9ec14d946ae6fabfb0aa3c8c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678586"
---
# <a name="idebugdocumentcontext2getsourcerange"></a>IDebugDocumentContext2::GetSourceRange
Získá zdrojový kód rozsah tohoto dokumentu kontextu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetSourceRange( 
   TEXT_POSITION* pBegPosition,
   TEXT_POSITION* pEndPosition
);
```

```csharp
int GetSourceRange( 
   TEXT_POSITION[] pBegPosition,
   TEXT_POSITION[] pEndPosition
);
```

#### <a name="parameters"></a>Parametry
 `pBegPosition`

 [out v] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která se vyplní počáteční pozice. Tento argument nastavena na hodnotu null, pokud tyto informace není potřeba.

 `pEndPosition`

 [out v] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která se vyplní koncovou pozici. Tento argument nastavena na hodnotu null, pokud tyto informace není potřeba.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Zdrojový rozsah je celý rozsah zdrojový kód z aktuální příkaz zpět jenom po předchozí prohlášení, které přispěly kódu. Zdrojový rozsah se obvykle používá ke kombinování příkazy zdrojového, včetně komentáře s kódem v okně zpětný překlad.

 Chcete-li získat oblasti pro pouze příkazy kódu obsažené v kontextu tohoto dokumentu, zavolejte [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)