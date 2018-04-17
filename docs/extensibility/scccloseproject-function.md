---
title: Funkce SccCloseProject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4f977c1241408f5e33d31a63262abb5ee24670e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="scccloseproject-function"></a>SccCloseProject – funkce
Tato funkce uzavře projektu, knec konkrétní relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 Struktura modulu plug-in kontextu řízení zdroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Projekt byl úspěšně uzavřen.|  
|SCC_E_PROJNOTOPEN|Žádný projekt je aktuálně otevřený.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 [SccOpenProject](../extensibility/sccopenproject-function.md) je vždy volána před provedením této funkce. Volání této funkce je následována volání buď `SccOpenProject` funkce nebo [SccUninitialize](../extensibility/sccuninitialize-function.md), který končí připojení k systému správy zdrojů úplně.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)