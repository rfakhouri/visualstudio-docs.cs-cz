---
title: Funkce SccGetCommandOptions | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetCommandOptions
helpviewer_keywords:
- SccGetCommandOptions function
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 60245b7fab3c2a0b313ccbe1d7393b0783962a37
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141194"
---
# <a name="sccgetcommandoptions-function"></a>SccGetCommandOptions – funkce
Tato funkce zobrazí výzvu pro rozšířené možnosti pro daný příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 rozhraní iCommand  
 [v] Příkaz, pro které jsou požadovány rozšířené možnosti (v tématu [příkaz kódu](../extensibility/command-code-enumerator.md) pro možné hodnoty).  
  
 ppvOptions  
 [v] Struktura možnost (může být také `NULL`).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěch.|  
|SCC_I_ADV_SUPPORT|Modul plug-in zdrojového kódu podporuje rozšířené možnosti pro příkaz.|  
|SCC_I_OPERATIONCANCELED|Uživatel zrušil zdroj ovládacího prvku plug v na **možnosti** dialogové okno.|  
|SCC_E_OPTNOTSUPPORTED|Modul plug-in správy zdroje nepodporuje tuto operaci.|  
|SCC_E_ISCHECKEDOUT|Nelze provést tuto operaci na soubor, který je právě rezervována.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Prostředí IDE volání této funkce poprvé s `ppvOptions` = `NULL` k určení, pokud modul plug-in zdrojového kódu podporuje funkci Rozšířené možnosti pro tento příkaz. Pokud modul plug-in podporuje funkci pro tento příkaz, rozhraní IDE zavolá tato funkce znovu až uživatel požádá rozšířené možnosti (obvykle implementovaný jako **Upřesnit** tlačítka v dialogovém okně) a poskytuje pro ukazateljinouhodnotunežNULL`ppvOptions` odkazující `NULL` ukazatel. Modul plug-in ukládá rozšířené možnosti zadanou uživatelem v Soukromá struktura a vrací ukazatel na této struktury v `ppvOptions`. Tato struktura je předána do všech dalších funkcí rozhraní API modulu Plugin zdroj ovládacího prvku, které potřebujete vědět o, včetně následných volání `SccGetCommandOptions` funkce.  
  
 Příklad mohou pomoci vysvětlení této situaci.  
  
 Uživatel rozhodne **získat** příkaz a rozhraní IDE zobrazuje **získat** dialogové okno. Volání IDE `SccGetCommandOptions` fungovat s `iCommand` nastavena na `SCC_COMMAND_GET` a `ppvOptions` nastavena na `NULL`. To je interpretována modulu plug-in jako otázka zdrojového kódu, "Máte rozšířené možnosti pro tento příkaz?" Pokud modul plug-in vrátí `SCC_I_ADV_SUPPORT`, rozhraní IDE zobrazuje **Upřesnit** tlačítko v jeho **získat** dialogové okno.  
  
 Prvním uživatel klikne **Upřesnit** tlačítko IDE znovu volá `SccGetCommandOptions` fungovat, tentokrát s jinou hodnotu než`NULL``ppvOptions` který odkazuje na `NULL` ukazatel. Modul plug-in zobrazí vlastní **získat možnosti** dialogové okno, vyzve uživatele k informace, uloží je do vlastní struktury a vrací ukazatel na této struktury v `ppvOptions`.  
  
 Pokud uživatel klikne na **Upřesnit** znovu v dialogovém okně stejné volá rozhraní IDE `SccGetCommandOptions` funkce znovu beze změny `ppvOptions`tak, aby strukturu je předán zpět do modulu plug-in. To umožňuje modul plug-in znovu inicializovat její dialogové okno na hodnoty, které uživatel dříve nastavené. Modul plug-in upravuje strukturu na místě před vrácením.  
  
 Nakonec, když uživatel klikne na **OK** v prostředí IDE **získat** dialogové okno, volání IDE [SccGet](../extensibility/sccget-function.md), předávání strukturu, vrátí se v `ppvOptions` obsahující Rozšířené možnosti.  
  
> [!NOTE]
>  Příkaz `SCC_COMMAND_OPTIONS` se používá, pokud rozhraní IDE zobrazuje **možnosti** dialogové, který umožňuje uživatelům nastavit předvolby, které řídí funkce integrace. Pokud modul plug-in zdrojového kódu se chce zadat vlastní dialogové okno Předvolby, se může zobrazit z **Upřesnit** tlačítka na dialogového okna předvoleb prostředí IDE. Modul plug-in je výhradně vaší zodpovědností pro získávání a zachování tyto informace; prostředí IDE není používat nebo jej upravit.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Příkaz kódu](../extensibility/command-code-enumerator.md)