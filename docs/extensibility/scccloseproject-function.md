---
title: Scccloseproject – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 67f0a7ee44f948c46a77f17234b139b271b66d1b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54947839"
---
# <a name="scccloseproject-function"></a>Scccloseproject – funkce
Tato funkce se zavře projekt knec konkrétní relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
### <a name="parameters"></a>Parametry  
 pvContext  
 Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Projekt byl úspěšně uzavřen.|  
|SCC_E_PROJNOTOPEN|Žádný projekt není otevřen.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 [Sccopenproject –](../extensibility/sccopenproject-function.md) je vždy volána před provedením této funkce. Voláním této funkce je následována volání na buď `SccOpenProject` funkce nebo [sccuninitialize –](../extensibility/sccuninitialize-function.md), které zcela ukončí připojení k systému správy zdrojového kódu.  
  
## <a name="see-also"></a>Viz také:  
 [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)