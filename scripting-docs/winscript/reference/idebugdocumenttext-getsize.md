---
title: IDebugDocumentText::GetSize | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetSize
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetSize
ms.assetid: 9da53856-613a-44b2-a84c-99454a2a1548
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95f8df44a503fa72f57a9cee17eb5e832e4eb670
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63008589"
---
# <a name="idebugdocumenttextgetsize"></a>IDebugDocumentText::GetSize
Vrátí počet řádků a počtu znaků v dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSize(  
   ULONG*  pcNumLines,  
   ULONG*  pcNumChars  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcNumLines`  
 [out] Počet řádků v dokumentu. Pokud má parametr hodnotu NULL, metoda nevrací hodnotu.  
  
 `pcNumChars`  
 [out] Počet znaků v dokumentu. Pokud má parametr hodnotu NULL, metoda nevrací hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí počet řádků a počtu znaků v dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText – rozhraní](../../winscript/reference/idebugdocumenttext-interface.md)