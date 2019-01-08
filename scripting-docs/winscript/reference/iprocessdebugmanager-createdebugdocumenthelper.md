---
title: IProcessDebugManager::CreateDebugDocumentHelper | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.CreateDebugDocumentHelper
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::CreateDebugDocumentHelper
ms.assetid: d644e192-1bcc-4768-a91e-239cd920adcd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62f61f00d2b5f850848efbcf3df65c5a3b10de3c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090480"
---
# <a name="iprocessdebugmanagercreatedebugdocumenthelper"></a>IProcessDebugManager::CreateDebugDocumentHelper
Vytvoří nového pomocníka dokumentu ladění pro tuto aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateDebugDocumentHelper(  
   IUnknown*               punkOuter,  
   IDebugDocumentHelper**  pddh  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `punkOuter`  
 [in] Pokud vrácený objekt je agregován, `punkOuter` je ukazatel rozhraní k řízení `IUnknown`. V opačném případě je ukazatel s hodnotou null.  
  
 `pddh`  
 [out] Ladění objekt pomocníka dokumentu pro tuto aplikaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří nový dokument pomocný ladění pro tuto aplikaci.  
  
## <a name="see-also"></a>Viz také  
 [IProcessDebugManager – rozhraní](../../winscript/reference/iprocessdebugmanager-interface.md)