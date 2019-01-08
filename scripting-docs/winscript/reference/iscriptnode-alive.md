---
title: IScriptNode::Alive | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Alive
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Alive
ms.assetid: d2755c83-e9b9-4c0a-acb7-25b554fc9fe8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 23f0e804cbbbe6683b89f7b629b9677c7b92c64f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089554"
---
# <a name="iscriptnodealive"></a>IScriptNode::Alive
Určuje, zda je objekt stále aktivní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Alive();  
```  
  
#### <a name="parameters"></a>Parametry  
 Metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Uzel skriptu je pořád aktivní.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud objekt není aktivní, modelu COM (Component Object) vrátí chybu z zařazování proxy serveru pro volání této metody.  
  
## <a name="see-also"></a>Viz také  
 [IScriptNode – rozhraní](../../winscript/reference/iscriptnode-interface.md)