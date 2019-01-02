---
title: Sccproperties – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 74eae3272563fb3514bedfd57fb3d94c98d98193
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53818846"
---
# <a name="sccproperties-function"></a>SccProperties – funkce
Tato funkce zobrazí vlastnosti správy zdrojového kódu pro soubor nebo projektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccProperties (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 lpFileName  
 [in] Název plně kvalifikovanou cestu k souboru nebo projektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěšně se zobrazí vlastnosti.|  
|SCC_I_RELOADFILE|Systém správy verzí změnil vlastnosti souboru, takže rozhraní IDE byste znovu načíst tento soubor.|  
|SCC_E_PROJNOTOPEN|Zadaný projekt nebyl otevřen ve správě zdrojového kódu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k zobrazení vlastností tohoto souboru nebo projektu.|  
|SCC_E_FILENOTCONTROLLED|K danému souboru nebo projektu není pod správou zdrojových kódů.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k neznámé nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in správy zdrojového kódu zobrazí v dialogovém okně Vlastní vlastnosti.  
  
 Vlastnosti jsou definovány pomocí modulu plug-in správy zdrojového kódu a může lišit od modulu plug-in pro modul plug-in. Pokud je modul plug-in umožňuje uživateli změnit vlastnosti ovládacího prvku zdrojového souboru, měla by vrátit `SCC_I_RELOAD` který signalizuje, že integrované vývojové prostředí, který tento soubor nebo projektu je potřeba znovu načíst.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)