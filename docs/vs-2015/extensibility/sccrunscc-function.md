---
title: Sccrunscc – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccRunScc
helpviewer_keywords:
- SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d2b36bd226d4eb19a694347edcba51812ee6f771
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190873"
---
# <a name="sccrunscc-function"></a>SccRunScc – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce vyvolá nástroj pro správu zdrojového ovládacího prvku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccRunScc(  
   LPVOID  pvContext,  
   HWND    hWnd,  
   LONG    nFiles,  
   LPCSTR* lpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 %{nfiles/  
 [in] Počet souborů podle `lpFileNames` pole.  
  
 lpFileNames  
 [in] Pole názvy vybraných souborů.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Value|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěšně byl vyvolán nástroj pro správu zdrojového ovládacího prvku.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena.|  
|SCC_E_INITIALIZEFAILED|Nepovedlo se inicializovat systém správy zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize.|  
|SCC_E_CONNECTIONFAILURE|Nepovedlo se připojit k systému správy zdrojového kódu.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není pod správou zdrojových kódů.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce umožňuje volajícímu přístup plný rozsah funkcí systému správy zdrojového kódu pomocí nástroje pro externí správu. Pokud systém správy zdrojového kódu nemá žádné uživatelské rozhraní, modul plug-in správy zdrojového kódu můžete implementovat rozhraní k provádění funkcí správy potřeby.  
  
 Tato funkce je volána s počet a pole názvů souborů pro aktuálně vybrané soubory. Pokud nástroj pro správu podporuje, seznam souborů, které slouží k předem vybere souborů v rozhraní pro správu; v opačném případě se dá ignorovat seznamu.  
  
 Tato funkce je obvykle vyvolány, když uživatel vybere **spuštění \<Server správy zdrojového kódu >** z **souboru** -> **správy zdrojových kódů** nabídka. To **spuštění** nabídky můžete vždy zakázané nebo dokonce skryté nastavením položky registru. Zobrazit [jak: Instalace modulu Plug-in zdrojového ovládacího prvku](../extensibility/internals/how-to-install-a-source-control-plug-in.md) podrobnosti. Tato funkce je volána, pouze pokud [sccinitialize –](../extensibility/sccinitialize-function.md) vrátí `SCC_CAP_RUNSCC` bit možnosti (naleznete v tématu [příznaky funkcí](../extensibility/capability-flags.md) podrobnosti o tomto a ostatní bity funkce).  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Postupy: Instalace modulu Plug-in správy zdrojového kódu](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Příznaky funkcí](../extensibility/capability-flags.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)
