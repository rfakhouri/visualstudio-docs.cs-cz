---
title: 'IScriptNode:: CreateChildEntry | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode. CreateChildEntry
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::CreateChildEntry
ms.assetid: b9682505-4457-40e9-8691-235843637506
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75369df719b0cd140ce621e916215eb18cf30a9e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58156655"
---
# <a name="iscriptnode-createchildentry"></a>IScriptNode:: CreateChildEntry
Přidá instanci podřízeného `IScriptEntry`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateChildEntry(  
   ULONG              isn,  
   DWORD              dwCookie,  
   LPCOLESTR          pszDelimiter,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `isn`  
 [in] Index pro podřízenou položku v nadřazeném prvku.  
  
 `dwCookie`  
 [in] Definované aplikací hodnotu slouží k přidružení položce podřízené hostitelský objekt.  
  
 `pszDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Pro analýzu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce bloku skriptu.  
  
 Oddělovač umožňuje skriptu pro vytváření stroji poskytovat předběžného zpracování. Modul může například nahradit jednoduchou uvozovku s dvěma jednoduchými uvozovkami pro použití jako oddělovače. Modul zjistí, jak se používá jako oddělovač.  
  
 Pokud oddělovač neoznačí konec bloku skriptu nastavena na hodnotu NULL.  
  
 `ppse`  
 [out] Adresa proměnné, která přijímá ukazatel `IScriptEntry` rozhraní instance podřízené.  
  
 Pro `IScriptNode` vrátí objekty, které představují webové stránky, tento parametr `IScriptEntry` instanci, která určuje blok skriptu.  
  
 Pro `IScriptEntry` vrátí objekty, které představují blok skriptu, tento parametr `IScriptEntry` instance, který určuje objekt funkce.  
  
 Pro `IScriptEntry` objekty, které představují funkce objektu, tato metoda se nezdaří.  
  
 Pro `IScriptScriptlet` objekty, tato metoda se nezdaří.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 `IScriptNode` Rozhraní představuje webovou stránku nebo jeho elementů. `IScriptEntry` Rozhraní (který je odvozen z `IScriptNode`) představuje blok skriptu nebo objekt funkce. `IScriptScriptlet` Rozhraní (který je odvozen z `IScriptEntry`) představuje obslužnou rutinu události.  
  
## <a name="see-also"></a>Viz také  
 [Iscriptnode – rozhraní](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)