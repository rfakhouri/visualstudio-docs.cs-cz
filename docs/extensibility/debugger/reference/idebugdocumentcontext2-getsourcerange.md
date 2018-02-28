---
title: IDebugDocumentContext2::GetSourceRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugDocumentContext2::GetSourceRange
helpviewer_keywords:
- IDebugDocumentContext2::GetSourceRange
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a7256771eed9e6d4ce12477dd34a63e8da06606e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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