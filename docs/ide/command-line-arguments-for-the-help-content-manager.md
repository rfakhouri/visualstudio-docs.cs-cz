---
title: Argumenty příkazového řádku pro správce obsahu nápovědy
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: reference
ms.assetid: 3aa9890a-1147-42ba-adea-17935d184038
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8a804ea329594a342a91c7f74e9ff32cd0206bed
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="command-line-arguments-for-the-help-content-manager"></a>Argumenty příkazového řádku pro správce obsahu nápovědy

Můžete určit, jak nasadit a spravovat místní obsah nápovědy pomocí argumenty příkazového řádku pro správce obsahu nápovědy (*HlpCtntMgr.exe*). Je nutné spustit skripty pro tento nástroj příkazového řádku s oprávněními správce a tyto skripty nelze spustit jako služby. Pomocí tohoto nástroje můžete provádět následující úlohy:

-   Přidat nebo aktualizovat místní obsah nápovědy z disku nebo do cloudu.

-   Odeberte místní obsah nápovědy.

-   Přesuňte místní úložiště obsahu nápovědy.

-   Přidání, aktualizace, odebrat nebo přesunout místní obsah nápovědy bezobslužně.

Syntaxe:

```
HlpCtntmgr.exe /operation Value /catalogname CatalogName /locale Locale /sourceuri InstallationPoint
```

Příklad:

```
hlpctntmgr.exe /operation install /catalogname VisualStudio15 /locale en-us /sourceuri d:\productDocumentation\HelpContentSetup.msha
```

## <a name="switches-and-arguments"></a>Přepínače a argumenty

Následující tabulka definuje přepínače a argumenty, které můžete použít pro nástroj příkazového řádku pro správce obsahu nápovědy:

|přepínače|Povinné?|Arguments|
|------------|---------------|---------------|
|/Operation|Ano|-   **Nainstalujte**– přidá knih z zdroji zadanou instalaci na místní ukládání obsahu.<br />     Tento přepínač vyžaduje /booklist argument, argumentem /sourceURI nebo obojí. Pokud nezadáte /sourceURI argument, výchozí Visual Studio URI slouží jako zdroj instalace. Pokud nezadáte /booklist argument, budou nainstalovány všechny knihy na /sourceUri.<br />-   **Odinstalace**– odebere knih, které zadáte z místního úložiště obsahu.<br />     Tento přepínač vyžaduje /booklist argument nebo /sourceURI argument.  Pokud zadáte /sourceURI argument, se odeberou všechny publikace a /booklist argument je ignorován.<br />-   **Přesunout**– přesune místní úložiště k cestě, kterou zadáte. Výchozí cesta místního úložiště je nastaven jako adresář v *ProgramData %*<br />     Tento přepínač vyžaduje argumenty /locationPath a /catalogName. Chybové zprávy se zaznamená do protokolu událostí, pokud zadáte cestu, která není platná nebo jednotka neobsahuje dost volného místa pro uložení obsahu.<br />-   **Aktualizujte**– aktualizace témata, které se změnily od byly nainstalovány nebo naposledy aktualizován.<br />     Tento přepínač vyžaduje /sourceURI argument.|
|/catalogName|Ano|Určuje název katalogu obsahu.|
|/Locale|Ne|Určuje národní prostředí produktu, který slouží k zobrazení a správě obsahu pro aktuální instanci programu Help Viewer. Můžete například zadat `EN-US` pro americkou angličtinu.<br /><br /> Pokud nezadáte v národním prostředí, použije se národní prostředí operačního systému. Pokud toto národní prostředí nelze určit, `EN-US` se používá.<br /><br /> Pokud jste určili v národním prostředí, které není platné, zaznamená se do protokolu událostí chybovou zprávu.|
|/e|Ne|Pokud má aktuální uživatel přihlašovací údaje pro správu, zvyšuje správce obsah nápovědy k oprávnění správce.|
|/sourceURI|Ne|Určuje adresu URL, ze kterého se obsah nainstalovat (Service API) nebo cestu k obsahu instalační soubor (*.msha*). Adresa URL může odkazovat Product Group (nejvyšší úrovně uzlu) nebo produktu knihách (uzel na úrovni listu) ve stylu koncový bod Visual Studio 2010. Nemusíte zahrnovat lomítko (/) na konci adresy URL. Pokud zahrnovat koncové lomítko, budou zpracovány správně.<br /><br /> Chybová zpráva se zaznamená do protokolu v případě protokolu Pokud zadáte soubor, který nebyl nalezen, není platný nebo není přístupná nebo pokud není k dispozici připojení k Internetu, nebo dojde k přerušení při obsah, který je spravován.|
|/ Vendor|Ne|Určuje dodavatele pro produkt obsah, který se odeberou (například `Microsoft`). Argument výchozí pro tento přepínač je Microsoft.|
|/ ProductName|Ne|Určuje název produktu knih, které se odeberou. Název produktu, je definovaný v *helpcontentsetup.msha* nebo *books.html* soubory, které byly dodány s obsahem. Najednou můžete odebrat knihy ze pouze jeden produkt. Odebrání knih z více produktů, je nutné provést několik instalace.|
|/booklist|Ne|Určuje názvy knih chcete spravovat, oddělené mezerami. Hodnoty musí odpovídat názvům adresáře jsou uvedeny na instalačním médiu.<br /><br /> Pokud nezadáte tento argument, budou nainstalovány všechny doporučené knihy pro zadaný produkt v /sourceURI.<br /><br /> Pokud název knihy obsahuje mezery, uzavřete ji do s dvojité uvozovky ("), aby se správně oddělený seznam.<br /><br /> Chybové zprávy bude do protokolu, pokud zadáte /sourceURI, která není platná nebo není dostupný.|
|/skuId|Ne|Určuje, skladovou jednotku (SKU) produktu z zdroje instalace a filtry knih, které identifikuje /SourceURI přepínače.|
|/Membership|Ne|-   **Minimální**– nainstaluje minimální sadu podle SKU, které zadáte pomocí přepínače /skuId obsahu nápovědy. Mapování mezi verze SKU a sady obsahu vystavený v Service API.<br />-   **Doporučená**– nainstaluje sadu Doporučené knihy pro SKU, které zadáte pomocí /skuId argument. Zdroj instalace je rozhraní API služby nebo *. MSHA*.<br />-   **Úplné**– nainstaluje celou sadu knih pro SKU, které zadáte pomocí /skuId argument. Zdroj instalace je rozhraní API služby nebo *. MSHA*.|
|/locationpath|Ne|Určuje výchozí složku pro místní obsah nápovědy. Tento přepínač je nutné použít pouze pro instalaci nebo přesunutí obsahu. Pokud zadáte tento přepínač, musíte zadat také silent přepínače.|
|/silent|Ne|Nainstaluje nebo odebere obsahu nápovědy bez výzvy pro uživatele nebo zobrazení uživatelského rozhraní, včetně ikony v oznamovací oblasti stav. Výstup se protokolují do souboru v *% Temp %* adresáře. **Důležité:** pro tichou instalaci obsahu, musíte použít digitálně podepsaných *.cab* souborů není *.mshc* soubory.|
|/launchingApp|Ne|Definuje aplikace a v kontextu katalogu při spuštění programu Help viewer bez s nadřazenou aplikací. Argumenty pro tento přepínač *#companyname*, *ProductName*, a *Cisloverze* (například `/launchingApp Microsoft,VisualStudio,15.0`).<br /><br /> Toto je požadováno pro instalaci obsahu s silent parametr.|
|/ wait *sekund*|Ne|Pozastaví nainstalujte, odinstalujte a aktualizujte operace. Pokud pro katalog již probíhá operace, bude proces počkat na zadaný počet sekund, chcete-li pokračovat. Použijte hodnotu 0 až po neomezenou dobu.|
|/?|Ne|Zobrazí seznam přepínačů a jejich popisy pro nástroj příkazového řádku pro správce obsahu nápovědy.|

### <a name="exit-codes"></a>Kódy ukončení

Když spustíte nástroj příkazového řádku pro obsah správce nápovědy v bezobslužném režimu, vrátí následující ukončovací kód:

```
Success = 0,

FailureToElevate = 100
InvalidCmdArgs = 101,
FailOnFetchingOnlineContent = 110,
FailOnFetchingContentFromDisk = 120,
FailOnFetchingInstalledBooks = 130,
NoBooksToUninstall = 200,
NoBooksToInstall = 300,
FailOnUninstall = 400,
FailOnInstall = 500,
FailOnMove = 600,
FailOnUpdate = 700,
FailOnRefresh = 800,
Cancelled = 900,
Others = 999,
ContentManagementDisabled = 1200,
OnlineHelpPreferenceDisabled = 1201
UpdateAlreadyRunning = 1300 - (Signals that the update didn't run because another was in progress.)
```

## <a name="see-also"></a>Viz také

- [Příručka správce Help Viewer](../ide/help-viewer-administrator-guide.md)
- [Přepsání Help Content Manager](../ide/help-content-manager-overrides.md)
- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)