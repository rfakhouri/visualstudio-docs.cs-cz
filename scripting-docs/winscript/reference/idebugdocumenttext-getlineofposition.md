---
title: IDebugDocumentText::GetLineOfPosition | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetLineOfPosition
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetLineOfPosition
ms.assetid: fe8d4802-ea16-49ca-8973-89dcaf6c915b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c916f0a76021afea82b4021ed1ce7d411317807
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087708"
---
# <a name="idebugdocumenttextgetlineofposition"></a>IDebugDocumentText::GetLineOfPosition
Vrátí číslo řádku a volitelně odsazení znaku v rámci řádku, který odpovídá dané pozici znaku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetLineOfPosition(  
   ULONG   cCharacterPosition,  
   ULONG*  pcLineNumber,  
   ULONG*  pcCharacterOffsetInLine  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cCharacterPosition`  
 [in] Počáteční umístění pozice rozsahu znaků.  
  
 `pcLineNumber`  
 [out] Číslo řádku rozsahu.  
  
 `pcCharacterOffsetInLine`  
 [out v] Odsazení znaku v rozsahu řádku `pcLineNumber`. Pokud je tento parametr `NULL`, metoda nevrací hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí číslo řádku a volitelně odsazení znaku v rámci řádku, který odpovídá dané pozici znaku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText – rozhraní](../../winscript/reference/idebugdocumenttext-interface.md)