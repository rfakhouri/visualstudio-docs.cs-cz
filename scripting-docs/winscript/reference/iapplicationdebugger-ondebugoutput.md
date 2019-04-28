---
title: IApplicationDebugger::onDebugOutput | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.onDebugOutput
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::onDebugOutput
ms.assetid: 978d8bcf-16dc-4f24-a6bc-206adee2b2e9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ffe4d56357a96dac8d5155ac2f8bd5182adef47e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991082"
---
# <a name="iapplicationdebuggerondebugoutput"></a>IApplicationDebugger::onDebugOutput
Zpracovává událost výstupu ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT onDebugOutput(  
   LPCOLESTR  pstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstr`  
 [in] Řetězec k zobrazení v ladicím programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Ladicí program obvykle zobrazí `pstr` v okně výstup.  
  
 Tato metoda je volána, když `IDebugApplication::DebugOutput` je volána.  
  
## <a name="see-also"></a>Viz také  
 [Iapplicationdebugger – rozhraní](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::DebugOutput](../../winscript/reference/idebugapplication-debugoutput.md)