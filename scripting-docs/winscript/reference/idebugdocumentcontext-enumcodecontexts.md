---
title: IDebugDocumentContext::EnumCodeContexts | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentContext.EnumCodeContexts
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentContext::EnumCodeContexts
ms.assetid: fb0aa64e-c458-4ef1-bcd8-5cebdc972549
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecf8b7d1ea292d0e1464825314cc92e1e903db3e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974420"
---
# <a name="idebugdocumentcontextenumcodecontexts"></a>IDebugDocumentContext::EnumCodeContexts
Vytvoří výčet kontexty kód spojený s tímto kontextem dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumCodeContexts(  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppescc`  
 [out] Kontexty kód spojený s tímto kontextem dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Dokument je obvykle přidružen pouze jeden kód kontextu, pokud je dokument vloženého souboru nebo šablonu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext – rozhraní](../../winscript/reference/idebugdocumentcontext-interface.md)