---
title: IDebugDocumentHelper::SetDefaultTextAttr | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetDefaultTextAttr
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetDefaultTextAttr
ms.assetid: 019a4191-0019-4376-bf70-89b33e7369de
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09f75e6f09639520462d5ef3983d67333097f76e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62948951"
---
# <a name="idebugdocumenthelpersetdefaulttextattr"></a>IDebugDocumentHelper::SetDefaultTextAttr
Nastaví výchozí atributy určený pro text, který není v bloku skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetDefaultTextAttr(  
   SOURCE_TEXT_ATTR  staTextAttr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `staTextAttr`  
 Výchozí atributy zdrojového textu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud výchozí atributy změní touto metodou, je výchozí atributy pro text mimo blok skriptu SOURCETEXT_ATTR_NONSOURCE. Uživatelské rozhraní tyto informace můžete použít k označení textu mimo bloky skriptu jako jen pro čtení.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHelper Interface](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)