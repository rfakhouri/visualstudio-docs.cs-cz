---
title: IDebugApplicationNode::Attach | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNode.Attach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationNode::Attach
ms.assetid: f4aad4ae-5bb0-4b5e-8f70-912a677f8f7a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49df95e2c5298fc9bb7025982e75a90548d9613f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094949"
---
# <a name="idebugapplicationnodeattach"></a>IDebugApplicationNode::Attach
Tento uzel aplikace přidá do stromu zadaný projekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Attach(  
   IDebugApplicationNode*  pdanParent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdanParent`  
 [in] Strom projektu, kde má být přidán tento uzel aplikace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda přidá do projektu tuto aplikaci uzlu stromové struktury, pomocí `pdanParent` jako nadřazený. Pokud `pdanParent` je `NULL`, uzlu tato aplikace bude uzel nejvyšší úrovně.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)   
 [IDebugApplicationNode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md)