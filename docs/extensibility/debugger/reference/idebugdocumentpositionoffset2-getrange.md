---
title: IDebugDocumentPositionOffset2::GetRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 65ae083dcc744f93948c03c6dfb3cd37ce265701
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
Načte rozsah pro aktuální pozici dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRange(  
   DWORD* pdwBegOffset,  
   DWORD* pdwEndOffset  
);  
```  
  
```csharp  
public int GetRange(  
   ref uint pdwBegOffset,  
   ref uint pdwEndOffset  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwBegOffset`  
 [ve out] Posun počáteční pozice rozsahu. Tento parametr nastavte na hodnotu null, pokud není nutné tyto informace.  
  
 `pdwEndOffset`  
 [ve out] Posunutí pro koncová pozice rozsahu. Tento parametr nastavte na hodnotu null, pokud není nutné tyto informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Rozsah zadaný v dokumentu pozici pro zarážek umístění používá stroj ladění (DE) k vyhledání dopředu příkaz, který ve skutečnosti přispívá kódu. Zvažte například následující kód:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Řádku 5 přispívá k programu laděné žádný kód. Pokud ladicí program, který nastaví zarážkou na řádku 5 chce DE budou prohledány určité množství pro první řádek, který přispívá kódu, chcete-li ladicí program zadejte rozsah, který obsahuje další candidate řádky, kde může správně umístit zarážku. DE by pak prohledávat dál tyto řádky dokud ho najít řádek, na kterém lze přijmout zarážky.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)   
 [Getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)