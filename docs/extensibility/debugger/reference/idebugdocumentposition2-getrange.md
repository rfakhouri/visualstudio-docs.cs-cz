---
title: IDebugDocumentPosition2::GetRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentPosition2::GetRange
helpviewer_keywords:
- IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db27be140cf47e0d070ba3c4f560a4ad89e68b83
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037262"
---
# <a name="idebugdocumentposition2getrange"></a>IDebugDocumentPosition2::GetRange
Získá rozsah pro tuto pozici dokumentu.  
  
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
 [out v] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která se vyplní počáteční pozice. Tento argument nastavena na hodnotu null, pokud tyto informace není potřeba.  
  
 `pEndPosition`  
 [out v] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která se vyplní koncovou pozici. Tento argument nastavena na hodnotu null, pokud tyto informace není potřeba.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Rozsah zadaný v dokumentu umístění pro zarážku umístění používá ladicí stroj (DE) pro hledání dopředu příkaz, který ve skutečnosti přispívá kódu. Zvažte například následující kód:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Řádek 5 přispívá k laděnému programu žádný kód. Pokud ladicí program, který nastaví zarážku na řádku 5 požaduje DE budou prohledány určité doby pro první řádek, jež přispívají kód, ladicí program zadáte rozsah, který obsahuje další Release candidate řádky, kde může být správně umístit zarážky. DE by pak hledá směrem dopředu pomocí tyto řádky až do nalezení řádek, který by mohl přijmout zarážku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)