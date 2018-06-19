---
title: IDebugDocumentContext2::GetSourceRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::GetSourceRange
helpviewer_keywords:
- IDebugDocumentContext2::GetSourceRange
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f003ba3f97f053c4617408bfc9334da057bb98ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107222"
---
# <a name="idebugdocumentcontext2getsourcerange"></a>IDebugDocumentContext2::GetSourceRange
Získá kód rozsah zdrojových tohoto kontextu dokumentu.  
  
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
 [ve out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která obsahuje počáteční pozici. Tento argument nastavte na hodnotu null, pokud není nutné tyto informace.  
  
 `pEndPosition`  
 [ve out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která obsahuje koncovou pozici. Tento argument nastavte na hodnotu null, pokud není nutné tyto informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Rozsah zdrojových je celý rozsah zdrojového kódu z aktuální příkaz zpět do právě po předchozí příkaz, který podílí kódu. Rozsah zdrojových se obvykle používá pro kombinování zdrojové příkazy včetně komentář s kódem v okně zpětný překlad.  
  
 Chcete-li získat rozsahu pro jenom příkazy kódu obsažené v tomto dokumentu kontextu, volejte [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)