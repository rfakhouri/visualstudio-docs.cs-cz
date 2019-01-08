---
title: Ijsdebugbreakpoint::getdocumentposition – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebugBreakPoint.GetDocumentPosition
apilocation:
- jscript9diag.dll
ms.assetid: 886df8ba-a59a-48a7-87f2-3b669e71528f
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d92a58dabe76e391d55996e511409fb63c9d671
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097666"
---
# <a name="ijsdebugbreakpointgetdocumentposition-method"></a>IJsDebugBreakPoint::GetDocumentPosition – metoda
Vrátí pozici prohlášení, kde byla zarážka vázána.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDocumentPosition(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocumentId`  
 [out] Jedinečné ID pro zdrojový dokument (ukazatel na IDebugDocumentText).  
  
 `pCharacterOffset`  
 [out] Odsazení znaku od nuly od začátku skriptu.  
  
 `pStatementCharCount`  
 [out] Délka aktuálního příkazu, který začíná * pCharacterOffset, ve znacích.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugBreakPoint – rozhraní](../../winscript/reference/ijsdebugbreakpoint-interface.md)