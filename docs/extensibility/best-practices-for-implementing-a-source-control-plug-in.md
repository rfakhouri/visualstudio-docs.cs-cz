---
title: "Osvědčené postupy pro implementaci zdrojového kódu, který je modul Plug-in | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, best practices
- best practices, source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: 85e73b73-29dc-464f-8734-ed308742c435
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9099d652012fb8b45b7b79f9c620f4102e7af602
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="best-practices-for-implementing-a-source-control-plug-in"></a>Osvědčené postupy pro implementaci modulu Plug-in Správa zdrojového kódu
Následující technické podrobnosti vám může pomoct spolehlivě implementovat zdrojového kódu v modulu plug-in [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="memory-management-issues"></a>Problémy s pamětí správy  
 Integrované vývojové prostředí (IDE), což je volající, ve většině případů uvolní a přidělí paměť. Modul plug-in správy zdroje vrátí řetězce a dalším položkám v přidělené volající vyrovnávací paměti. Výjimky jsou uvedeny v popisech specifické funkce, které se vyskytují.  
  
## <a name="arrays-of-file-names"></a>Pole názvy souborů  
 Pokud není předán pole souborů není předán jako souvislý pole názvů souborů. Je předán jako pole ukazatele na názvy souborů. Například v [SccGet](../extensibility/sccget-function.md), jsou názvy souborů předaná `lpFileNames` parametr, kde `lpFileNames` je ve skutečnosti ukazatel na `char **`. `lpFileNames`[0] je ukazatel na křestní jméno, `lpFileNames`[1]. je zde ukazatel na druhý název a tak dále.  
  
## <a name="large-model"></a>Velké modelu  
 Všechny odkazy jsou 32bitová verze i v operačních systémech 16 bitů.  
  
## <a name="fully-qualified-paths"></a>Úplné cesty  
 Kde názvy souborů nebo adresářů jsou zadané jako argumenty, musí být plně kvalifikované cesty nebo cesty UNC, bez koncová zpětná lomítka. Je zodpovědností modul plug-in převede do relativní cesty, pokud tedy požadavek základní správy zdrojového kódu zdrojového kódu.  
  
## <a name="specify-a-fully-qualified-path-for-the-registered-dll"></a>Zadejte plně kvalifikovanou cestu pro registrované knihovny DLL  
 Prostředí IDE už načte knihovny DLL z relativní cesty (například.\NewProvider.dll). Úplná cesta knihovny DLL musí zadat (například C:\Providers\NewProvider.dll). Tento požadavek posiluje zabezpečení integrovaného vývojového prostředí tím, že načítání ovládacího prvku neoprávněným nebo zosobněnou zdroje knihovny DLL.  
  
## <a name="check-for-an-existing-vssci-plug-in-when-you-install-your-source-control-plug-in"></a>Kontrola existující modul Plug-in VSSCI při instalaci modulu Plug-in vašeho zdrojového kódu  
 Uživatel, který plánuje nainstalovat modul plug-in správy zdroje už pravděpodobně máte existující zdroj ovládacího prvku modulu plug-in v počítači nainstalována. Instalace programu pro modul plug-in, abyste vytvořili by měl zjistit, zda je existující hodnoty pro klíče registru relevantní. Pokud tyto klíče jsou již nastaveny, instalační program musí požádat uživatele ohledně zaregistrujte se jako modul plug-in správy zdroje výchozí modul plug-in a nahraďte ten, který je již nainstalován.  
  
## <a name="error-result-codes-and-reporting"></a>Chybové kódy výsledků a vytváření sestav  
 `SCC_OK` Vrátí kód pro funkci řízení zdroj označuje, že operace proběhl úspěšně pro všechny soubory. Pokud se operace nezdaří, očekává se, že vrátit poslední kód chyby.  
  
 Pravidla pro vytváření sestav je, že pokud dojde k chybě v prostředí IDE, rozhraní IDE je zodpovědná za nahlášeny. Pokud dojde k chybě v systému správy zdrojů, zdrojového kódu modul plug-in je zodpovědný za nahlášeny. Například "žádné soubory aktuálně vybrané" by být hlášených rozhraní IDE, zatímco "Tento soubor je již rezervován" by oznámeny pomocí modulu plug-in.  
  
## <a name="the-context-structure"></a>Struktura kontextu  
 Během volání [SccInitialize](../extensibility/sccinitialize-function.md), předává volající `ppvContext` parametr, který je neinicializovaný popisovač pro void. Správa zdrojového kódu modul plug-in můžete ignorovat tento parametr nebo ji můžete přidělit struktura libovolného typu a ukazatel na této struktury do předaný ukazatele. Prostředí IDE nerozumí tuto strukturu, ale předá ukazatel na tuto strukturu do každé volání v modulu plug-in. To poskytuje informace o mezipaměti cenné kontextu v modulu plug-in, můžete použít ke správě globální stav informací, která je uchována napříč volání funkce bez použití globální proměnné. Modul plug-in je zodpovědný za uvolnění strukturu na volání [SccUninitialize](../extensibility/sccuninitialize-function.md).  
  
 Pokud modul plug-in sady `SCC_CAP_REENTRANT` bit ve [SccInitialize](../extensibility/sccinitialize-function.md) (konkrétně v `lpSccCaps` parametr), více struktury kontextu se používají ke sledování všechny projekty, které jsou otevřené.  
  
## <a name="bitflags-and-other-command-options"></a>Bitové příznaky a další možnosti příkazu  
 U každého příkazu, jako [SccGet](../extensibility/sccget-function.md), IDE, můžete zadat mnoho možností, které mění chování příkazu.  
  
 Rozhraní API podporuje nastavení určitých možností IDE prostřednictvím `fOptions` parametr. Tyto možnosti jsou popsané v [bitové příznaky používané určité příkazy](../extensibility/bitflags-used-by-specific-commands.md) společně s příkazy, které mají vliv. Obecně platí jsou tyto možnosti, pro které by se uživateli výzva.  
  
 Většina uživatelsky konfigurovatelného nastavení možnosti nejsou definovány tímto způsobem, protože se lišit široce zdroj ovládacího prvku zásuvné moduly. Proto je doporučené mechanismus **Upřesnit** tlačítko. Například v **získat** dialogové okno, rozhraní IDE zobrazuje pouze informace, které se rozumí, ale zobrazí se také **Upřesnit** tlačítko, pokud má modul plug-in parametry tohoto příkazu. Když uživatel klikne **Upřesnit** tlačítko, volání IDE [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) povolit modul plug-in požádat uživatele o informace, například bitové příznaky nebo datum/čas zdrojového kódu. Modul plug-in vrátí tyto informace ve struktuře, která je předán zpět během `SccGet` příkaz.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../extensibility/internals/creating-a-source-control-plug-in.md)