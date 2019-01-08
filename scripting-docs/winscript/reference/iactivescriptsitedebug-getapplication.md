---
title: IActiveScriptSiteDebug::GetApplication | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetApplication
ms.assetid: 4400f1b1-3108-4a71-b1f1-43586fe1227c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a485a7195f64754bc28d0c1905d30d6f22747c31
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090113"
---
# <a name="iactivescriptsitedebuggetapplication"></a>IActiveScriptSiteDebug::GetApplication
Vrátí objekt ladění aplikace související s touto lokalitou skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppda`  
 [out] Ukazatel na objekt aplikace ladění přidružené k lokalitě skriptu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Hostitel nepodporuje přímo ladění.|  
  
## <a name="remarks"></a>Poznámky  
 `GetApplication` Metoda poskytuje způsob, jakým inteligentního hostitele k definování tohoto objektu aplikace, ke kterému patří každý skript. Skriptovací stroje má pokusit o volat tuto metodu za účelem získání jejich obsahující aplikace a uchýlíte k `IProcessDebugManager::GetDefaultApplication` Pokud se to nezdaří.  
  
## <a name="see-also"></a>Viz také  
 [Iactivescriptsitedebug – rozhraní](../../winscript/reference/iactivescriptsitedebug-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)