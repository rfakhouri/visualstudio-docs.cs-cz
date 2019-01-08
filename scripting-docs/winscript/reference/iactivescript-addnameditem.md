---
title: IActiveScript::AddNamedItem | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- AddNamedItem method, IActiveScript interface
ms.assetid: a7c6317d-948f-4bb3-b169-1bbe5b7c7cc5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ae4a84821d0db226cbecb01e329e4f2941a675d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095092"
---
# <a name="iactivescriptaddnameditem"></a>IActiveScript::AddNamedItem
Přidá do oboru názvů skriptovací stroj název položky kořenové úrovně. Kořenovou položku je objekt s vlastností a metod, zdroj událostí nebo všechny tři.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddNamedItem(  
    LPCOLESTR pstrName,  // address of item name  
    DWORD dwFlags          // item flags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky, jak je zobrazuje ze skriptu. Název musí být jedinečný a trvalé.  
  
 `dwFlags`  
 [in] Příznaky spojené s položkou. Může být kombinací těchto hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTITEM_CODEONLY|Označuje, že pojmenovanou položku představuje objekt jen pro kód a že hostitel nemá žádné `IUnknown` mají být spojeny s tímto objektem pouze kód. Hostitel má jenom název pro tento objekt. Tento příznak by objektově orientované jazyků C++, vytvořte třídu. Ne všechny jazyky podporují tento příznak.|  
|SCRIPTITEM_GLOBALMEMBERS|Označuje, že položka je kolekce globální vlastnosti a metody asociované s skriptu. Za normálních okolností byste skriptovací stroj ignorovat název objektu (jiné než za účelem použití jako soubor cookie pro [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) metodu, nebo pro vyřešení explicitní oborů) a zobrazit její členy jako globální proměnné a metody. To umožňuje hostiteli rozšíření knihovny (běhové funkce a tak dále) k dispozici ke skriptu. Je ponecháno na vypořádat s názvem skriptovací stroj je v konfliktu (například když dvě položky SCRIPTITEM_GLOBALMEMBERS mají metody se stejným názvem), i když by neměl být vrácena chyba z důvodu této situaci.|  
|SCRIPTITEM_ISPERSISTENT|Označuje, že položka by měla uložit, pokud je uložen skriptovací stroj. Podobně, nastavením tohoto příznaku označuje, že přechod zpět do stavu spuštění by měl uchovávat informace názvem a typem položky (skriptovací stroj musí však uvolnit všechny odkazy na rozhraní na objekt, který vede).|  
|SCRIPTITEM_ISSOURCE|Označuje, že položka zdrojem událostí, které můžete skript jímky. Podřízené objekty (vlastnosti objektu, které jsou v samotné objekty) můžete také zdroje událostí do skriptu. Nejedná se o rekurzivní, ale poskytuje vhodný mechanismus pro běžné, například vytvoření kontejneru a všechny její členské ovládací prvky.|  
|SCRIPTITEM_ISVISIBLE|Označuje, zda je název položky k dispozici v oboru názvu souboru, který umožňuje přístup k vlastnosti, metody a události položky. Podle konvence vlastnosti položky patří podřízené položky; proto všechny podřízený objekt vlastnosti a metody (a jejich podřízených rekurzivně) budou mít přístup.|  
|SCRIPTITEM_NOCODE|Označuje, že položka je jednoduše název přidávané do oboru názvů vašeho skriptu a by neměla být zpracována jako položku, pro který kód by měl být přidružené. Bez tento příznak nastaven, například VBScript se vytvoří samostatný modul s názvem položky a C++ může vytvořit samostatný obálkovou třídu s názvem položky.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)