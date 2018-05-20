---
title: Vývoj osvědčené postupy pro COM, VSTO a VBA doplňky v Office
ms.custom: ''
ms.date: 07/25/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- ''
helpviewer_keywords:
- ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 020faeb330348049dcf12431fadfa6ab099d1584
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="development-best-practices-for-com-vsto-and-vba-add-ins-in-office"></a>Vývoj osvědčené postupy pro COM, VSTO a VBA doplňky v Office
  Pokud vyvíjíte COM, postupujte podle VSTO nebo VBA pro vytváření doplňků pro Office, vývoj osvědčené postupy, které jsou popsané v tomto článku.   To pomůže zajistit:

-  Kompatibilita doplňky mezi různými verzemi a nasazení systému Office.
-  Jednodušší nasazení doplňku pro vaše uživatele a správce IT.
-  Nedojde k neúmyslnému instalace nebo modul runtime selhání tohoto doplňku.

>Poznámka: Pomocí [plochy most](/windows/uwp/porting/desktop-to-uwp-root) Příprava vašeho modelu COM, VSTO nebo VBA doplňku pro Windows Store se nepodporuje. Doplňky COM, VSTO a VBA nelze distribuovat úložiště systému Windows nebo Office úložiště. 
  
## <a name="do-not-check-for-office-during-installation"></a>Nekontrolovat Office během instalace  
 Nedoporučujeme mít vaše add-in zjistit, zda je nainstalována Office během procesu instalace doplňku. Pokud není nainstalovaná Office, můžete nainstalovat doplněk a uživatel bude mít přístup k po dokončení instalace sady Office. 
  
## <a name="use-embedded-interop-types-nopia"></a>Použití vložené typy spolupráce (NoPIA)  
Pokud řešení používá rozhraní .NET 4.0 nebo novější, použijte vložené typy spolupráce (NoPIA) místo v závislosti na Office primární zprostředkovatel komunikace s objekty sestavení (primární) redistributable. Pomocí typu vložení snižuje velikost instalace řešení a k zajištění budoucí kompatibility. Office 2010 byl poslední verzi systému Office, která odeslaná PIA redistributable. Další informace najdete v tématu [návod: vložení informací o typu ze sestavení sady Microsoft Office](https://msdn.microsoft.com/en-us/library/ee317478.aspx) a [ekvivalence typů a vestavěné typy spolupráce](/windows/uwp/porting/desktop-to-uwp-root).

Pokud řešení používá starší verzi rozhraní .NET, doporučujeme aktualizovat vaše řešení, aby používalo rozhraní .NET 4.0 nebo novější. Pomocí rozhraní .NET 4.0 nebo novější snižuje požadavky modulu runtime v novějších verzích systému Windows.
  
## <a name="avoid-depending-on-specific-office-versions"></a>Vyhněte se v závislosti na konkrétních verzí systému Office  
Pokud řešení používá funkce, které jsou k dispozici v novější verzi systému Office, ověřte, zda funkce existuje (Pokud je to možné, na úrovni funkcí) za běhu (například používání výjimek zpracování nebo kontrolou verze). Ověřit minimální verze, místo konkrétních verzí, pomocí podporovaných rozhraní API v objektovém modelu, například [Application.Version vlastnost](https://msdn.microsoft.com/en-us/library/office/microsoft.office.interop.excel._application.version.aspx). Není doporučeno, protože tyto můžete volit mezi instalací, prostředí a verze závisí na binární metadata, instalační cesty nebo klíčů registru.

## <a name="enable-both-32-bit-and-64-bit-office-usage"></a>Povolit 32bitové a 64bitové verze Office využití   
Váš výchozí cíl sestavení by měly podporovat (x86) 32bitové i 64bitové (x64), pokud vaše řešení závisí na knihovny, které jsou dostupné pouze pro konkrétní počet bitů. Přijetí, zejména v prostředích velkých objemů dat roste 64bitová verze systému Office. Podpora 32bitových a 64-bit usnadňuje uživatelům přechod mezi 32bitové a 64bitové verze systému Office.

Při psaní kódu pro jazyk VBA, použijte 64-bit bezpečné deklarovat příkazy a proveďte převod proměnné podle potřeby. Dále ověřte, že dokumenty lze sdílet mezi uživateli, kteří používají 32bitovou nebo 64bitovou verzí systému Office zadáním kódu pro každý počtu bitů. Další informace najdete v tématu [64-bit Visual Basic pro aplikace – přehled](https://msdn.microsoft.com/en-us/library/office/gg264421.aspx).

## <a name="support-restricted-environments"></a>Podpora prostředí s omezeným přístupem   
Řešení by neměl vyžadovat zvýšení oprávnění účtu uživatele nebo správce oprávnění. Kromě toho by neměl řešení závisí na nastavení nebo změna:

- Aktuální pracovní adresář.
- Knihovny DLL načíst adresáře.
- Proměnné PATH.

## <a name="change-the-save-location-of-shared-data-and-settings"></a>Změnit uložení umístění sdílených dat a nastavení
Pokud řešení se skládá z doplňku a proces, který je externí Office, nepoužívejte složku dat aplikací uživatele nebo registru pro výměnu dat nebo nastavení mezi doplněk a externího procesu. Místo toho zvažte použití dočasné složky uživatele, složku Dokumenty nebo instalační adresář vaše řešení.

## <a name="increment-the-version-number-with-each-update"></a>Zvýšit číslo verze se jednotlivé aktualizace
Nastaví číslo verze binárních souborů ve vašem řešení a zvýší při každé aktualizaci. To bude usnadňují uživatelům identifikovat změny mezi verzemi a vyhodnocení kompatibility.

## <a name="provide-support-statements-for-the-latest-versions-of-office"></a>Zadejte příkazy podpory pro nejnovější verze sady Office
Zákazníci žádáme ISV poskytnout příkazy podpory pro jejich COM, VSTO VBA doplňky a které běží v Office. Výpis zákazníky pomáhá příkazy explicitní podporu pomocí Office 365 ProPlus připravenosti nástroje pochopit podporu. 

Pokud chcete zadat příkazy podpory pro klientské aplikace sady Office (například Word nebo Excel), nejdřív ověřte, zda doplňky spustit v aktuální verzi Office a pak potvrzení poskytovat aktualizace, pokud vaše doplněk dělí v budoucí verzi. Nemáte k testování doplňků při vydání nového sestavení nebo aktualizace Office. Microsoft zřídka mění rozšiřitelnost platformy COM, VSTO a VBA v Office a tyto změny budou dobře zdokumentovat.

>Důležité: Microsoft udržuje seznam podporovaných doplňky pro připravenosti sestavy a ISV kontaktní informace. Doplněk uvedené získáte v tématu [ https://aka.ms/readyforwindows ](https://aka.ms/readyforwindows).

## <a name="use-process-monitor-to-help-debug-installation-or-loading-issues"></a>Použijte nástroj Sledování procesu pomáhají ladit instalace nebo načítání problémy
Pokud vaše doplněk má problémy s kompatibilitou při instalaci nebo zatížení, mohou být s problémy s přístupem k souborům a registru. Použití [monitorování procesu](/sysinternals/downloads/procmon) nebo podobné ladicí nástroj protokolování a porovnání chování proti pracovního prostředí, aby bylo možné identifikovat problém.
