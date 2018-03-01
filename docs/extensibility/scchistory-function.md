---
title: Funkce SccHistory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: cf621b3050382d79fcf44df2ac5d50d9885e03d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="scchistory-function"></a>SccHistory – funkce
Tato funkce zobrazí historii zadané soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvContext`  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 `hWnd`  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 `nFiles`  
 [v] Počet souborů zadaný v `lpFileName` pole.  
  
 `lpFileName`  
 [v] Pole plně kvalifikované názvy souborů.  
  
 `fOptions`  
 [v] Příkaz příznaky (aktuálně nepoužívá se).  
  
 `pvOptions`  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Historie verzí byla byly úspěšně načteny.|  
|SCC_I_RELOADFILE|Správy zdrojového kódu ve skutečnosti změnil soubor na disku při načítání historii (například získáním stará verze), a integrovaného vývojového prostředí by měl znovu zavést tento soubor.|  
|SCC_E_FILENOTCONTROLLED|Soubor není ve správě zdrojového kódu.|  
|SCC_E_OPNOTSUPPORTED|Správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_PROJNOTOPEN|Projekt je nebyl otevřen.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě. Nebylo možné získat historie souborů.|  
  
## <a name="remarks"></a>Poznámky  
 Správa zdrojového kódu modulu plug-in můžete zobrazit svůj vlastní dialogové okno Zobrazit historii jednotlivých souborů pomocí `hWnd` jako nadřazeného okna. Alternativně volitelný textový výstup zpětného volání funkce zadané [SccOpenProject](../extensibility/sccopenproject-function.md) lze použít, pokud je podporováno.  
  
 Všimněte si, že za určitých okolností, jedná o prohlížení může změnit během provádění toto volání. Například [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] historie příkaz umožňuje uživateli možnost získat stará verze souboru. V takovém případě zdroj řízení modulu plug-in vrátí `SCC_I_RELOAD` IDE upozornit, že je nutné znovu načíst soubor.  
  
> [!NOTE]
>  Pokud modul plug-in správy zdroje nepodporuje tuto funkci pro pole souborů, mohou být zobrazeny pouze historie souborů pro první soubor.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)