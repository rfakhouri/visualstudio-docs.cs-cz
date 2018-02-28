---
title: Funkce SccPopulateDirList | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4be6e63df26d3c4a9b6539276aa97f69e349b83c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList – funkce
Tato funkce určuje, které adresářů a (volitelně) souborů jsou uložené ve správě zdrojového kódu, předložen seznam adresáře, které chcete prověřit.  
  
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
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 nDirs  
 [v] Počet cesty adresářů v `lpDirPaths` pole.  
  
 lpDirPaths  
 [v] Pole cesty adresářů prozkoumat.  
  
 pfnPopulate  
 [v] Funkce zpětného volání k volání pro každou cesta k adresáři a (volitelně) název souboru v `lpDirPaths` (viz [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) podrobnosti).  
  
 pvCallerData  
 [v] Hodnota, která má být předán beze změny funkce zpětného volání.  
  
 fOptions  
 [v] Kombinace hodnot, které řídí zpracování adresáře (naleznete v části "PopulateDirList příznaky" [bitové příznaky používané určité příkazy](../extensibility/bitflags-used-by-specific-commands.md) pro možné hodnoty).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace se úspěšně dokončila.|  
|SCC_E_UNKNOWNERROR|Došlo k chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Pouze adresáře a (volitelně) názvy souborů, které jsou ve skutečnosti v úložiště řízení zdrojů se předávají do funkce zpětného volání.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Bitové příznaky, které používá konkrétní příkazy](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [Chybové kódy](../extensibility/error-codes.md)