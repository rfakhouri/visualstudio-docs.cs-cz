---
title: Sccuninitialize – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8dba45116c956c1edc1a8ffb691397375345c661
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967203"
---
# <a name="sccuninitialize-function"></a>SccUninitialize – funkce
Tato funkce vyčistí všechny přidělení nebo otevřená připojení vytvořili podle předchozího volání [sccinitialize –](../extensibility/sccinitialize-function.md) při přípravě na vypínání modulu plug-in správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] V vytvoří ukazatel na strukturu modulu plug-in kontext zdrojového ovládacího prvku [sccinitialize –](../extensibility/sccinitialize-function.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Vyčištění byla úspěšně dokončena.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in správy zdrojového kódu je zodpovídá za připravuje se vypnout a uvolnit paměť, která má modul plug-in přidělené pro strukturu kontext. Funkce se volá jednou pro každou instanci daného modulu plug-in. Volání [sccinitialize –](../extensibility/sccinitialize-function.md) předchází toto volání. Žádné projekty nadále možné otevřít v okamžiku volání `SccUninitialize`.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)