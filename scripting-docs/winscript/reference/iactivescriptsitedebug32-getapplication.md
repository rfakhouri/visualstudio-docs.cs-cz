---
title: IActiveScriptSiteDebug32::GetApplication | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 533d770d-06a4-4693-873e-255c9c6f0df0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: c71e33445db7745f71e374c586d079a9665776b2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992484"
---
# <a name="iactivescriptsitedebug32getapplication"></a>IActiveScriptSiteDebug32::GetApplication
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
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Hostitel nepodporuje přímo ladění.|  
  
## <a name="remarks"></a>Poznámky  
 `GetApplication` Metoda poskytuje způsob, jakým inteligentního hostitele k definování tohoto objektu aplikace, ke kterému patří každý skript. Skriptovací stroje má pokusit o volat tuto metodu za účelem získání jejich obsahující aplikace a uchýlíte k `IProcessDebugManager::GetDefaultApplication` Pokud se to nezdaří.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteDebug32 Interface](../../winscript/reference/iactivescriptsitedebug32-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)