---
title: IScriptNode::GetParent | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetParent
ms.assetid: 0fb813f6-ab94-46b2-b0cf-ef5d1cd38ae4
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b45fc7be1a5178e952fefcd794171410d149a1f4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090022"
---
# <a name="iscriptnodegetparent"></a>IScriptNode::GetParent
Vrátí `IScriptNode` objekt, který je nadřazeného člena objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppsnParent`  
 [out] Adresa proměnné, která přijímá ukazatel `IScriptNode` rozhraní nadřazená instance.  
  
 Pokud třída implementuje `IScriptEntry` nebo `IScriptScriptlet`, `IScriptNode` je vrácen objekt.  
  
 Pokud třída implementuje `IScriptNode` (představující webovou stránku), vrátí se hodnota NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IScriptNode – rozhraní](../../winscript/reference/iscriptnode-interface.md)