---
title: POPLISTFUNC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- POPDIRLISTFUNC
helpviewer_keywords:
- POPLISTFUNC callback function
ms.assetid: b2199fd5-d707-4628-92dd-e2a01e2f507a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dc15af65c6541df5ef77a3bdc85ee0e59fa20991
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="poplistfunc"></a>POPLISTFUNC
Je součástí této zpětného volání [SccPopulateList](../extensibility/sccpopulatelist-function.md) zařízení IDE a je používána modulu plug-in zdrojového kódu se aktualizovat seznam souborů a složek (také zadaný do `SccPopulateList` funkce).  
  
 Když uživatel vybere **získat** příkazů v prostředí IDE, rozhraní IDE zobrazuje seznam všech souborů, které může uživatel získat. Bohužel IDE nezná přesný seznam všech souborů, které může uživatel získat; pouze modul plug-in má tento seznam. Pokud ostatní uživatelé přidali soubory do projektu správy zdrojového kódu, tyto soubory by se zobrazit v seznamu, ale IDE nebude vědět o nich. Prostředí IDE sestavuje seznam souborů, které se domnívá, že uživatel může získat. Než se uživateli zobrazí tento seznam, zavolá [SccPopulateList](../extensibility/sccpopulatelist-function.md) `,` poskytnutí modulu plug-in zdrojového kódu šanci na Přidat a odstranit soubory ze seznamu.  
  
## <a name="signature"></a>Podpis  
 Modul plug-in správy zdroje upraví seznamu voláním funkce implementované IDE s následující prototyp:  
  
```cpp  
typedef BOOL (*POPLISTFUNC) (  
   LPVOID pvCallerData,  
   BOOL fAddRemove,  
   LONG nStatus,  
   LPSTR lpFileName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 `pvCallerData` Parametr předaný volající (IDE) [SccPopulateList](../extensibility/sccpopulatelist-function.md). Modul plug-in zdrojového kódu by měla předpokládají nic o obsah tohoto parametru.  
  
 fAddRemove  
 Pokud `TRUE`, `lpFileName` je soubor, který musí být přidaní do seznamu souborů. Pokud `FALSE`, `lpFileName` je soubor, který měl by být odstraněn ze seznamu souborů.  
  
 nStatus  
 Stav `lpFileName` (kombinaci `SCC_STATUS` bits; viz [souboru stavový kód](../extensibility/file-status-code-enumerator.md) podrobnosti).  
  
 lpFileName  
 Úplná cesta k adresáři názvu souboru můžete přidat nebo odstranit ze seznamu.  
  
## <a name="return-value"></a>Návratová hodnota  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`TRUE`|Modul plug-in můžete dál volání této funkce.|  
|`FALSE`|Na straně IDE (například z důvodu nedostatku paměti situaci) došlo k potížím. Modul plug-in by se měla zastavit operaci.|  
  
## <a name="remarks"></a>Poznámky  
 Pro každý soubor, který chce, aby se modul plug-in zdrojového kódu pro přidání nebo odebrání ze seznamu souborů, zavolá tato funkce předávání v `lpFileName`. `fAddRemove` Příznak znamená vytvoření nového souboru přidejte do seznamu nebo starý soubor odstranit. `nStatus` Parametr poskytuje stav souboru. Po dokončení přidávání a odstraňování souborů modulu plug-in SCC vrátí z [SccPopulateList](../extensibility/sccpopulatelist-function.md) volání.  
  
> [!NOTE]
>  `SCC_CAP_POPULATELIST` Bit možnosti je vyžadována pro Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání, které implementují rozhraní IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)   
 [Soubor stavový kód](../extensibility/file-status-code-enumerator.md)