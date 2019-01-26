---
title: Sccpopulatedirlist – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 79eb0bdfdcb9f0b64258128b801e65f257e0ed3e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949945"
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList – funkce
Tato funkce určuje, které adresářů a (volitelně) souborů jsou uložené ve správě zdrojového kódu v daném seznamu adresáře ke kontrole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 nDirs  
 [in] Počet cesty k adresářům v `lpDirPaths` pole.  
  
 lpDirPaths  
 [in] Pole cesty k adresářům prozkoumat.  
  
 pfnPopulate  
 [in] Funkce zpětného volání volat pro každou cestu k adresáři a (volitelně) název souboru v `lpDirPaths` (viz [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) podrobnosti).  
  
 pvCallerData  
 [in] Hodnota, která má být předán funkci zpětného volání beze změny.  
  
 fOptions  
 [in] Kombinace hodnot, které řídí, jak se zpracovávají v adresářích (naleznete v části "PopulateDirList flags" [příznaky Bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md) možných hodnot).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace se úspěšně dokončila.|  
|SCC_E_UNKNOWNERROR|Došlo k chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Pouze těch adresářů a (volitelně) názvy souborů, které jsou ve skutečnosti v úložišti správy zdrojů, jsou předány funkci zpětného volání.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Příznaky Bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [Chybové kódy](../extensibility/error-codes.md)