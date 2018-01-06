---
title: IDebugDocumentPosition2::GetRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentPosition2::GetRange
helpviewer_keywords: IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0b570591777eb00f200af7541d781fe2778e63ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentposition2getrange"></a>IDebugDocumentPosition2::GetRange
Získá rozsahu pro tuto pozici dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetRange(   
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
 Rozsah zadaný v dokumentu pozici pro zarážek umístění používá stroj ladění (DE) k vyhledání dopředu příkaz, který ve skutečnosti přispívá kódu. Zvažte například následující kód:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Řádku 5 přispívá k programu laděné žádný kód. Pokud ladicí program, který nastaví zarážkou na řádku 5 chce DE budou prohledány určité množství pro první řádek, který přispívá kódu, chcete-li ladicí program zadejte rozsah, který obsahuje další candidate řádky zarážku může správně umístění. DE by pak prohledávat dál tyto řádky dokud ho najít řádek, na kterém lze přijmout zarážky.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)