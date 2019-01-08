---
title: IScriptNode::GetChild | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetChild
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetChild
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55cd6cf5233e850e4109128e322d3fc5bd0b1355
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086590"
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
Vrací podřízeného, který je k zadanému indexu v uzlu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `isn`  
 [in] Index pro podřízenou položku v nadřazeném prvku.  
  
 `ppsn`  
 [out] Adresa proměnné, která přijímá ukazatel `IScriptNode` rozhraní instance podřízené.  
  
 Pro `IScriptNode` objekty, které představují webové stránky, tento parametr vrátí objekt, který obsahuje blok skriptu.  
  
 Pro `IScriptEntry` objekty, které určují blok skriptu, vrátí objekt, který určuje funkci, která tento parametr.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Pro `IScriptEntry` objekty, které určují objekt funkce a `IScriptScriptlet` objekty, tato metoda se nezdaří, protože neobsahuje žádné podřízené položky.  
  
## <a name="see-also"></a>Viz také  
 [IScriptNode – rozhraní](../../winscript/reference/iscriptnode-interface.md)