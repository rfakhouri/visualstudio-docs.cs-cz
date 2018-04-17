---
title: Funkce SccDiff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccDiff
helpviewer_keywords:
- SccDiff function
ms.assetid: d49bc8c5-f631-4153-9d3c-feb3564da305
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 30d8d6a4b8b400088d5feed663c8257215a0f8a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccdiff-function"></a>SccDiff – funkce
Tato funkce zobrazí (nebo volitelně právě vyhledává) rozdíly mezi aktuální soubor (na místním disku) a jeho poslední verze, vráceno se změnami ve zdroji řízení systému.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccDiff(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LPCSTR    lpFileName,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpFileName  
 [v] Název souboru, pro které je požadováno rozdíl.  
  
 fOptions  
 [v] Příkaz příznaky. Podrobnosti najdete v části poznámky.  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Pracovní verze kopírování a serveru jsou stejné.|  
|SCC_I_FILESDIFFERS|Je pracovní kopie se liší od verze v části Správa zdrojového kódu.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
|SCC_E_FILENOTCONTROLLED|Soubor není ve správě zdrojového kódu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR|Nespecifikované chybě; nebyla získat soubor rozdíl.|  
|SCC_E_FILENOTEXIST|Místní soubor nebyl nalezen.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce slouží dva různé účely. Ve výchozím nastavení zobrazí seznam změny do souboru. Modul plug-in zdrojového kódu se otevře vlastní okno, v jakémkoli formátu rozhodne, chcete-li zobrazit rozdíly mezi uživatele soubor na disku a nejnovější verzi souboru ve správě zdrojového kódu.  
  
 Alternativně IDE může jednoduše je potřeba určit, zda došlo ke změně souboru. Prostředí IDE může například potřebovat k určení, zda je bezpečné rezervovat soubor bez informující uživatele. V takovém případě předá prostředí IDE `SCC_DIFF_CONTENTS` příznak. Modul plug-in zdrojového kódu musí zkontrolujte soubor na disku, bajt po bajtu proti řízenou zdrojový soubor a vrátí hodnotu, která určuje, zda jsou dva soubory bez zobrazení nic uživateli jiný.  
  
 Stejně jako optimalizace výkonu, modul plug-in zdrojového kódu použít alternativu na základě kontrolní součet nebo časové razítko místo volá pro porovnání bajtové byte `SCC_DIFF_CONTENTS`: tyto formuláře porovnání jsou samozřejmě rychlejší, ale méně spolehlivé. Ne všechny systémy správy zdrojového může podporovat tyto metody alternativní porovnání a modul plug-in může být nutné vrátit zpět k porovnání obsahu. Všechny zdrojové řízení moduly plug-in musí, minimálně, podporovat porovnání obsahu.  
  
> [!NOTE]
>  Příznaky rychlé rozdíl se vzájemně vylučují. Je platný předat žádné příznaky, ale není platné. současně předat více než jednou. `SCC_DIFF_QUICK_DIFF`, což je masku, která spojuje všechny příznaky, dá použít k testování, ale jeho nikdy mají být předány jako parametr.  
  
|`fOption`|Význam|  
|---------------|-------------|  
|SCC_DIFF_IGNORECASE|Porovnávání (lze použít pro rychlé nebo visual rozdíl).|  
|SCC_DIFF_IGNORESPACE|Ignoruje mezer (lze použít pro rychlé nebo visual rozdíl).|  
|SCC_DIFF_QD_CONTENTS|Bezobslužná porovná soubor bajtů podle bajtů.|  
|SCC_DIFF_QD_CHECKSUM|Bezobslužná porovná soubor prostřednictvím kontrolního součtu, pokud je podporovaná. Pokud není podporován, přejde k porovnání obsahu.|  
|SCC_DIFF_QD_TIME|Bezobslužná porovná soubor prostřednictvím její časové razítko, pokud je podporovaná. Pokud není podporován, přejde k porovnání obsahu.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)