---
title: Funkce SccCheckin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccCheckin
helpviewer_keywords: SccCheckin function
ms.assetid: e3f26ac2-6163-42e1-a764-22cfea5a3bc6
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f95377f79d02952c63b673d50569fac058a8573c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="scccheckin-function"></a>SccCheckin – funkce
Tato funkce zkontroluje v dříve rezervovaných souborů do správy zdrojového kódu, ukládání změn a vytváření novou verzi. Tato funkce je volána s počet a pole názvy souborů se změnami.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCheckin (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPSTR*    lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, SCC modulu plug-in pro všechna dialogová okna poskytuje můžete jako nadřazený objekt.  
  
 : %{nfiles/  
 [v] Počet souborů, které chcete vrátit se změnami.  
  
 lpFileNames  
 [v] Pole úplná místní cesta názvy souborů se změnami.  
  
 lpComment  
 [v] Komentář má být použita pro každou z vybraných souborů, které se změnami. Toto je `NULL` Pokud modul plug-in zdrojového kódu by se zobrazit výzva pro komentář.  
  
 fOptions  
 [v] Příkaz příznaky, buď 0 nebo `SCC_KEEP_CHECKEDOUT`.  
  
 pvOptions  
 [v] SCC plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Soubory byla úspěšně vrácena se změnami.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není ve správě zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě. Soubor nebyl změnami.|  
|SCC_E_NOTCHECKEDOUT|Uživatel není rezervována soubor, takže nelze zkontrolovat.|  
|SCC_E_CHECKINCONFLICT|Vrácení se změnami nelze provést, protože:<br /><br /> -Jiný uživatel má dopředu změnami a `bAutoReconcile` je chybná.<br /><br /> -nebo-<br /><br /> -Automatické sloučení nelze provést, (například, pokud jsou binární soubory).|  
|SCC_E_VERIFYMERGE|Soubor byl sloučit automaticky, ale nebyla vrácena čeká na ověření uživatele.|  
|SCC_E_FIXMERGE|Soubor byl sloučit automaticky, ale nebyla vrácena z důvodu konfliktu sloučení, který je třeba vyřešit ručně.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
|SCC_E_FILENOTEXIST|Místní soubor nebyl nalezen.|  
  
## <a name="remarks"></a>Poznámky  
 Komentář platí pro všechny soubory se změnami. Argument komentář může mít `null` řetězce, modul plug-in zdrojového kódu v takovém případě můžete požádat uživatele o řetězec komentář pro každý soubor.  
  
 `fOptions` Argument je možné přidělit hodnotu `SCC_KEEP_CHECKEDOUT` příznak indikující uživatele záměr zkontrolujte v souboru a znovu ji rezervovat.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)