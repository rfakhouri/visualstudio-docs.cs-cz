---
title: Sccpopulatedirlist – funkce | Dokumentace Microsoftu
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
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 358512c94f46971cc91ef3ed065c83ba56e5ad16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666292"
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sccpopulatedirlist – funkce](https://docs.microsoft.com/visualstudio/extensibility/sccpopulatedirlist-function).  
  
Tato funkce určuje, které adresářů a (volitelně) souborů jsou uložené ve správě zdrojového kódu v daném seznamu adresáře ke kontrole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccPopulateDirList(  
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

