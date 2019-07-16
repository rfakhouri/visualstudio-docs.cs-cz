---
title: Scccloseproject – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7d2364215f528f16d05ecf0c53b152f7334f4b4a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68156135"
---
# <a name="scccloseproject-function"></a>SccCloseProject – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce se zavře projekt knec konkrétní relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
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
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)
