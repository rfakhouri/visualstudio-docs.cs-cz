---
title: Scccloseproject – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aebc9d43ebf712d8add7e2aee4f7884ef2754da6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629715"
---
# <a name="scccloseproject-function"></a>SccCloseProject – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [scccloseproject – funkce](https://docs.microsoft.com/visualstudio/extensibility/scccloseproject-function).  
  
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
 [Sccopenproject –](../extensibility/sccopenproject-function.md)   
 [Sccinitialize –](../extensibility/sccinitialize-function.md)

