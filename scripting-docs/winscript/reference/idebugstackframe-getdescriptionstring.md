---
title: IDebugStackFrame::GetDescriptionString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrame.GetDescriptionString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetDescriptionString
ms.assetid: a2ddc069-c440-4dee-98dc-ab7c78773b94
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f870c6dbc654f8465d201c53443228153ce4a68b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62934614"
---
# <a name="idebugstackframegetdescriptionstring"></a>IDebugStackFrame::GetDescriptionString
Vrátí krátký nebo long textový popis rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDescriptionString(  
   BOOL   fLong,  
   BSTR*  pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fLong`  
 [in] Příznak, kde `TRUE` vrátí dlouhý popis a `FALSE` vrátí krátký popis.  
  
 `pbstrDescription`  
 [out] Popis rámce zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Obvykle Pokud `fLong` je `FALSE`, tato metoda poskytuje pouze název funkce související s rámce zásobníku. Když `fLong` je `TRUE`, tato metoda může taky poskytnout parametry funkce a další relevantní informace.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame – rozhraní](../../winscript/reference/idebugstackframe-interface.md)