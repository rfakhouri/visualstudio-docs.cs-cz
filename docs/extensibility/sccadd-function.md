---
title: Funkce SccAdd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccAdd
helpviewer_keywords:
- SccAdd function
ms.assetid: 545268f3-8e83-446a-a398-1a9db9e866e8
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 52137da9d14920a2fd5213f1110a74d895e51c7f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccadd-function"></a>SccAdd – funkce
Tato funkce přidá nové soubory do správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccAdd(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG*     pfOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 : %{nfiles/  
 [v] Počet souborů, které chcete přidat do aktuálního projektu jak je uveden v `lpFileNames` pole.  
  
 lpFileNames  
 [v] Pole plně kvalifikované názvy místních souborů, které chcete přidat.  
  
 lpComment  
 [v] Komentář, který má být použita pro všechny soubory, který chcete přidat.  
  
 pfOptions  
 [v] Pole příznaky příkazu, k dispozici na základě podle souborů.  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace přidání byla úspěšná.|  
|SCC_E_FILEALREADYEXISTS|Vybraný soubor je již ve správě zdrojového kódu.|  
|SCC_E_TYPENOTSUPPORTED|Typ souboru (například binární) nepodporuje správy zdrojového kódu.|  
|SCC_E_OPNOTSUPPORTED|Správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_NONSPECIFICERROR|Nespecifikované chybě; přidáte, nelze provést.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
|SCC_E_FILENOTEXIST|Místní soubor nebyl nalezen.|  
  
## <a name="remarks"></a>Poznámky  
 Obvyklé `fOptions` se zde nahrazují pole, `pfOptions`, s jedním `LONG` možnost specifikace na soubor. Je to proto, že typ souboru se může lišit od souboru do souboru.  
  
> [!NOTE]
>  Není možné zadat oba seznamy `SCC_FILETYPE_TEXT` a `SCC_FILETYPE_BINARY` možnosti pro stejného souboru, ale je platná k určení ani jeden z nich. Nastavení ani jeden z nich je stejné jako nastavení `SCC_FILETYPE_AUTO`, v takovém případě zdroj řízení modulu plug-in automatické typ souboru.  
  
 Níže uvádíme seznam příznaky, které jsou používány `pfOptions` pole:  
  
|Možnost|Hodnota|Význam|  
|------------|-----------|-------------|  
|SCC_FILETYPE_AUTO|0x00|Modul plug-in zdrojového kódu by měl zjistit typ souboru.|  
|SCC_FILETYPE_TEXT|0x01|Určuje textový soubor ASCII.|  
|SCC_FILETYPE_BINARY|0x02|Určuje typ souboru než ASCII text.|  
|SCC_ADD_STORELATEST|0x04|Ukládá pouze nejnovější verzi souboru žádné rozdíly.|  
|SCC_FILETYPE_TEXT_ANSI|0x08|Zpracuje soubor jako text v kódu ANSI.|  
|SCC_FILETYPE_UTF8|0x10|Zpracuje soubor jako text v kódu Unicode ve formátu UTF8.|  
|SCC_FILETYPE_UTF16LE|0x20|Zpracuje soubor jako text v kódu Unicode v UTF16 trochu Endian formátu.|  
|SCC_FILETYPE_UTF16BE|0x40|Vyhodnotí formátu souboru jako text v kódu Unicode v UTF16 Big Endian.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)