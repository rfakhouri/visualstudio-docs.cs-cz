---
title: Funkce SccRunScc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccRunScc
helpviewer_keywords:
- SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 322ebe148144260106fb895273b66e1b9f5696f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138262"
---
# <a name="sccrunscc-function"></a>SccRunScc – funkce
Tato funkce vyvolá nástroj pro správu zdroj ovládacího prvku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccRunScc(  
   LPVOID  pvContext,  
   HWND    hWnd,  
   LONG    nFiles,  
   LPCSTR* lpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 : %{nfiles/  
 [v] Počet souborů zadaný v `lpFileNames` pole.  
  
 lpFileNames  
 [v] Pole názvy vybraného souboru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Nástroje pro správu řízení zdroj byl úspěšně vyvolán.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena.|  
|SCC_E_INITIALIZEFAILED|Nepodařilo se inicializovat správy zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí.|  
|SCC_E_CONNECTIONFAILURE|Nepodařilo se připojit k systému správy zdrojů.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není ve správě zdrojového kódu.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce umožňuje volajícímu přístup prostřednictvím nástroje pro správu externí plný rozsah funkcí správy zdrojového kódu. Pokud správy zdrojového kódu nemá žádné uživatelské rozhraní, modul plug-in zdrojového kódu můžete implementovat rozhraní k provádění funkcí správy nezbytné.  
  
 Tato funkce je volána s počet a pole názvy souborů pro aktuálně vybrané soubory. Pokud ji podporuje nástroj pro správu, seznam souborů, které slouží k předem vybrat soubory v rozhraní správy; v seznamu, jinak můžete ignorovat.  
  
 Tato funkce je volána obvykle, když uživatel vybere **spusťte \<zdrojového ovládacího prvku serveru >** z **soubor** -> **správy zdrojového kódu** nabídky. To **spusťte** nabídky můžete vždy zakázáno nebo i skryté nastavením položky registru. V tématu [postupy: Instalace modulu Plugin zdroj ovládacího prvku](../extensibility/internals/how-to-install-a-source-control-plug-in.md) podrobnosti. Tato funkce je volána, pouze pokud [SccInitialize](../extensibility/sccinitialize-function.md) vrátí `SCC_CAP_RUNSCC` bit možnosti (v tématu [schopností příznaky](../extensibility/capability-flags.md) podrobnosti o tomto a dalších schopností bits).  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Postupy: Instalace modulu Plug-in Správa zdrojového kódu](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Příznaky schopností](../extensibility/capability-flags.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)