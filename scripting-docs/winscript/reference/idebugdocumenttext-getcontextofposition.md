---
title: IDebugDocumentText::GetContextOfPosition | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetContextOfPosition
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetContextOfPosition
ms.assetid: 86560853-d9b1-499a-a1b5-ea06aa1f1f5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2eb889bef17d2038f17c7f8618ad65ca2162f0c7
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097588"
---
# <a name="idebugdocumenttextgetcontextofposition"></a>IDebugDocumentText::GetContextOfPosition
Vytvoří objekt kontextu dokumentu odpovídající pozice rozsahu zadaný znak.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetContextOfPosition(  
   ULONG                    cCharacterPosition,  
   ULONG                    cNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cCharacterPosition`  
 [in] Počáteční umístění pozice rozsahu znaků.  
  
 `cNumChars`  
 [in] Počet znaků v rozsahu.  
  
 `ppsc`  
 [out] Objekt kontextu dokumentu odpovídající pozice rozsahu zadaný znak.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří objekt kontextu dokumentu odpovídající pozice rozsahu zadaný znak.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText – rozhraní](../../winscript/reference/idebugdocumenttext-interface.md)