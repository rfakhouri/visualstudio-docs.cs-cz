---
title: Funkce SccDirDiff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccDirDiff
helpviewer_keywords: SccDirDiff function
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea335ef6bcb2a27b4312c613062be0d365711cbc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sccdirdiff-function"></a>SccDirDiff – funkce
Tato funkce zobrazí rozdíly mezi aktuálním místním adresáři na disku klienta a odpovídající projekt ve správě zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpDirName  
 [v] Plně kvalifikovaná cesta k místnímu adresáři, pro které chcete zobrazit visual rozdíl.  
  
 dwFlags  
 [v] Příkaz příznaky (viz poznámku části).  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Adresáře na disku je stejný jako projekt ve správě zdrojového kódu.|  
|SCC_I_FILESDIFFER|Adresáře na disku se liší od do správy zdrojového kódu projektu.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
|SCC_E_FILENOTCONTROLLED|Adresář není ve správě zdrojového kódu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
|SCC_E_FILENOTEXIST|Místní adresář nelze nalézt.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce slouží k dá pokyn modulu plug-in pro uživatele zobrazíte seznam změn do zadaného adresáře zdrojového kódu. Modul plug-in otevře vlastní okno, ve formátu podle svého výběru, chcete-li zobrazit rozdíly mezi adresáři uživatele na disku a odpovídající projekt ve správě verzí.  
  
 Pokud modul plug-in podporuje porovnání adresáře na všech, ho musí podporovat porovnání adresáře na základě názvu souboru i v případě, že možnosti "rychlé rozdílové" nejsou podporovány.  
  
|`dwFlags`|Interpretace|  
|---------------|--------------------|  
|SCC_DIFF_IGNORECASE|Porovnávání (lze použít pro rychlé rozdílové nebo visual).|  
|SCC_DIFF_IGNORESPACE|Ignoruje mezer (lze použít pro rychlé rozdílové nebo visual).|  
|SCC_DIFF_QD_CONTENTS|Pokud podporovaná modulu plug-in zdrojového kódu, porovná bezobslužně adresáři bajtů podle bajtů.|  
|SCC_DIFF_QD_CHECKSUM|Pokud podporuje modul plug-in, bezobslužně porovná adresáři prostřednictvím kontrolní součet nebo, pokud není podporován, spadne zpět na SCC_DIFF_QD_CONTENTS.|  
|SCC_DIFF_QD_TIME|Pokud podporuje modul plug-in, bezobslužně porovná adresáři prostřednictvím její časové razítko nebo, pokud není podporován, spadne zpět na SCC_DIFF_QD_CHECKSUM nebo SCC_DIFF_QD_CONTENTS.|  
  
> [!NOTE]
>  Tato funkce používá stejné příznaky příkazu jako [SccDiff](../extensibility/sccdiff-function.md). Správa zdrojového kódu modulu plug-in však rozhodnout operace "rychlé rozdílové" pro adresáře není podporována.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)