---
title: Sccgetextendedcapabilities – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f02591eac6a3f69ae5513aa9dc0abed381cd1c8a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775404"
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce vrací další funkce, podporuje modul plug-in správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 lSccExCaps  
 [in] Příznak určující rozšířené možnosti pro kterou chcete otestovat (viz tabulka pro rozšířené funkce kódu [příznaky funkcí](../extensibility/capability-flags.md) příznaků je to možné).  
  
 pbSupported  
 [out] Vrátí nenulovou (`TRUE`) Pokud zadaná funkce se podporuje; v opačném případě vrátí hodnotu 0 (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace get funkce byla úspěšně dokončena.|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Došlo k neznámé nebo neurčené chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána na vyžádání; To znamená, když funkce se musí otestovat, tato metoda je volána k určení, zda, která možnost je podporována. Je zadán pouze jeden příznak najednou.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Kódy chyb](../extensibility/error-codes.md)   
 [Příznaky funkcí](../extensibility/capability-flags.md)
