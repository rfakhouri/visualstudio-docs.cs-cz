---
title: Funkce SccProperties | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: efaa2877743fcf69a61a79633108d203442489e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccproperties-function"></a>SccProperties – funkce
Tato funkce zobrazí vlastnosti zdroje ovládací prvek pro soubor nebo projektu.  
  
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
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpFileName  
 [v] Název plně kvalifikovanou cestu k souboru nebo projektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěšně se zobrazí vlastnosti.|  
|SCC_I_RELOADFILE|Systém správy verzí změnil vlastnosti souboru a integrovaného vývojového prostředí by měl znovu zavést tento soubor.|  
|SCC_E_PROJNOTOPEN|Zadaný projekt nebyl otevřen ve správě zdrojového kódu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k zobrazení vlastností tento soubor nebo projektu.|  
|SCC_E_FILENOTCONTROLLED|Zadaný soubor nebo projektu není ve správě zdrojového kódu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k neznámé nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in zdrojového kódu zobrazí v dialogovém okně Vlastní vlastnosti.  
  
 Vlastnosti jsou definovány pomocí modulu plug-in zdrojového kódu a může lišit od modulu plug-in modulu plug-in. Pokud je modul plug-in umožňuje uživatelům změnit vlastnosti ovládacího prvku zdrojového souboru, by měla vrátit `SCC_I_RELOAD` signál IDE, který tento soubor nebo projektu potřebujete znovu načíst.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)