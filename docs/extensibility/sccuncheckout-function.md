---
title: Funkce SccUncheckout | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccUncheckout
helpviewer_keywords: SccUncheckout function
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f9b4b2f06b8ee020ca07e780836ec2abbbc96e82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccuncheckout-function"></a>SccUncheckout – funkce
Tato funkce vrátí zpět předchozí operace checkout, a tak obnovit obsah vybraného souboru nebo soubory do stavu před rezervaci. Všechny změny provedené v souboru od rezervaci budou ztraceny.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
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
 [v] Pole úplná místní cesta názvy souborů, pro které chcete vrátit zpět checkout.  
  
 fOptions  
 [v] Příkaz příznaky (nepoužívá se).  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Najdete v článku věnovaném vrácení zpět byla úspěšná.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není ve správě zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě. Vrátit zpět rezervaci nebylo úspěšné.|  
|SCC_E_NOTCHECKEDOUT|Uživatel nemá soubor rezervovaný.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_PROJNOTOPEN|Projekt nebyl otevřen od správy zdrojového kódu.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="remarks"></a>Poznámky  
 Po provedení této operace `SCC_STATUS_CHECKEDOUT` a `SCC_STATUS_MODIFIED` příznaky oba soubory se odstraní pro soubory, na kterých byla provedena operace vrácení zpět checkout.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)