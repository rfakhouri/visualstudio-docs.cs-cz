---
title: 'Postupy: Instalace modulu Plug-in Správa zdrojového kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], source control plug-ins
- source control plug-ins, installing
ms.assetid: 9e2e01d9-7beb-42b2-99b2-86995578afda
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4ffabd7adf35956163c8744eae6539e96990f38a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-install-a-source-control-plug-in"></a>Postupy: Instalace modulu Plug-in Správa zdrojového kódu
Vytvoření ovládacího prvku zdroj modulu plug-in zahrnuje tři kroky:  
  
1.  Vytvořte knihovny DLL s funkcí definovaných v části referenční dokumentace rozhraní API modulu Plugin řízení zdroj této dokumentace.  
  
2.  Implementace rozhraní API modulu Plugin zdroj ovládacího prvku definované funkce. Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hovory, zpřístupnit rozhraní a dialogových oknech z modulu plug-in.  
  
3.  Zaregistruje knihovnu DLL tak, že položky odpovídající registru.  
  
## <a name="integration-with-visual-studio"></a>Integrace se sadou Visual Studio  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporuje zdroj ovládacího prvku moduly plug-in odpovídajících směrnicím rozhraní API ovládacího prvku Plug-in zdroje.  
  
### <a name="registering-the-source-control-plug-in"></a>Registrace modulu Plug-in zdrojového kódu  
 Než spuštěné integrované vývojové prostředí (IDE) můžete volat do správy zdrojového kódu, musí nejprve najít zdroj řízení knihovnu DLL modulu plug-in, který exportuje rozhraní API.  
  
##### <a name="to-register-the-source-control-plug-in-dll"></a>Zaregistrujte zdroj řízení knihovnu DLL modulu plug-in  
  
1.  Přidáte dvě položky pod klíčem HKEY_LOCAL_MACHINE v podklíči SOFTWARE, který určuje podklíč název vaší společnosti následuje vaší podklíč název produktu. Vzor je HKEY_LOCAL_MACHINE\SOFTWARE\\*[název společnosti]*\\*[název produktu]*\\*[položka]* = hodnota. Dvě položky se nazývají vždy SCCServerName a SCCServerPath. Každá je regulární řetězec.  
  
     Například pokud je název vaší společnosti Microsoft a vaší zdrojové řízení produkt jmenuje SourceSafe, pak by tato cesta v registru HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe. V tomto podklíči první položka, SCCServerName, je uživatelem čitelný řetězec pojmenování svůj produkt. Druhá položka SCCServerPath, je úplná cesta ke zdroji řízení knihovnu DLL modulu plug-in, který by se měly připojit rozhraní IDE. Následující tabulka obsahuje ukázkové položky registru:  
  
    |Vstup vzorového registru|Hodnota vzorku|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerName|Microsoft Visual SourceSafe|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerPath|c:\vss\win32\ssscc.dll|  
  
    > [!NOTE]
    >  SCCServerPath je úplná cesta k SourceSafe modulu plug-in. Modul plug-in správy zdroje použije odlišné názvy produktů a společnosti ale stejné cesty položky registru.  
  
2.  Následující položky registru volitelné umožňuje upravovat chování modul plug-in správy zdroje. Tyto položky přejděte v podklíči stejné jako SccServerName a SccServerPath.  
  
    -   Položka HideInVisualStudioregistry lze použít, pokud nechcete, aby váš zdroj ovládacího prvku plug v zobrazí v seznamu výběru Plug-in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Tato položka také ovlivní automatického přepínání k řízení zdrojů, modul plug-in. Možné použití tato položka je-li zadat zdrojový balíček ovládací prvek, který nahrazuje modul plug-in správy zdroje, ale chcete, aby bylo snazší pro uživatele k migraci z pomocí modulu plug-in pro zdrojový balíček pro řízení zdrojového kódu. Pokud zdrojový balíček ovládací prvek je nainstalovaná, nastaví tato položka registru skryje modulu plug-in.  
  
         HideInVisualStudio hodnotu DWORD a je nastavená na 1 ke skrytí modul plug-in nebo 0, chcete-li zobrazit modul plug-in. Pokud položku registru nezobrazí, použije se výchozí chování je zobrazit modulu plug-in.  
  
    -   Položku registru DisableSccManager lze zakázat nebo skrýt **spusťte \<zdrojového ovládacího prvku serveru >** nabídky, která obvykle se zobrazí pod **soubor**  ->   **Ovládací prvek zdroje** dílčí nabídky. Výběrem této nabídky možnost volání [SccRunScc](../../extensibility/sccrunscc-function.md) funkce. Modul plug-in správy zdroje nemusí podporovat vnějšímu programu a proto můžete chtít zakázat nebo i skrýt **spusťte** možnost nabídky.  
  
         DisableSccManager je hodnotu DWORD nastavena na 0, chcete-li povolit **spusťte \<zdrojového ovládacího prvku serveru >** nabídky, nastavena na hodnotu 1, chcete-li zakázat možnost nabídky a skrytí nabídky možnost nastaven na hodnotu 2. Pokud tato položka registru nezobrazí, použije se výchozí chování je zobrazit položku nabídky.  
  
    |Vstup vzorového registru|Hodnota vzorku|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\HideInVisualStudio|1|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\DisableSccManager|1|  
  
3.  Přidejte podklíč, SourceCodeControlProvider, pod klíčem HKEY_LOCAL_MACHINE v podklíči softwaru.  
  
     V tomto podklíči položku registru ProviderRegKey nastavena na řetězec, který představuje podklíč, který jste umístili v registru v kroku 1. Vzor je HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey = softwaru\\*[název společnosti]*\\*[název produktu]*.  
  
     Zde je ukázkový obsah pro tento podklíč.  
  
    |Položky registru|Hodnota vzorku|  
    |--------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  Modul plug-in správy zdroje používat stejné podklíč a názvy položek, ale hodnota se bude lišit.  
  
4.  Vytvořit podklíč s názvem InstalledSCCProviders v podklíči SourceCodeControlProvider a umístěte jedna položka v tomto podklíči.  
  
     Název této položky je uživatelem čitelný název zprostředkovatele (stejný jako hodnota zadaná pro položku SCCServerName) a hodnota je znovu podklíč vytvořili v kroku 1. Vzor je HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders\\*[zobrazovaný název]* = softwaru\\*[název společnosti]* \\ *[název produktu]*.  
  
     Příklad:  
  
    |Vstup vzorového registru|Hodnota vzorku|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders\Microsoft Visual SourceSafe|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  Může být několik zdroj ovládacího prvku modulů plug-in registrované tímto způsobem. Jedná se jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] najde všechny nainstalované založené na rozhraní API modulu Plugin zdroj ovládacího prvku moduly plug-in.  
  
## <a name="how-an-ide-locates-the-dll"></a>Jak IDE vyhledává knihovny DLL  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE má dva způsoby, jak najít zdroj řízení knihovnu DLL modulu plug-in:  
  
-   Najít zdrojového kódu pro výchozí modul plug-in a připojte se k němu bezobslužně.  
  
-   Ovládací prvek moduly plug-in, najít všechny registrované zdroj, u ze kterého uživatel zvolí jeden.  
  
 První způsobem najít knihovnu DLL, vypadá rozhraní IDE pro položku ProviderRegKey v podklíči HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider. Hodnota této položky se odkazuje na jiný podklíč. Prostředí IDE pak hledá položku s názvem SccServerPath v této druhé podklíčem v HKEY_LOCAL_MACHINE. Hodnota této položky odkazuje na knihovnu DLL rozhraní IDE.  
  
> [!NOTE]
>  Prostředí IDE nenačte knihovny DLL z relativní cesty (například.\NewProvider.DLL). Musíte zadat úplnou cestu k souboru DLL (například c:\Providers\NewProvider.DLL). To brání načítání knihoven DLL modulu plug-in neoprávněným nebo zosobněnou posiluje zabezpečení rozhraní IDE.  
  
 Druhý způsobem najít knihovnu DLL, vypadá rozhraní IDE pro všechny položky v podklíči HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider\InstalledSCCProviders*.* Každá položka má název a hodnotu. Rozhraní IDE zobrazuje seznam tyto názvy pro uživatele*.* Když uživatel vybere název, vyhledá rozhraní IDE pro vybraný název, který odkazuje na podklíč hodnota. Položka s názvem SccServerPath v tomto podklíči pod HKEY_LOCAL_MACHINE vyhledá rozhraní IDE. Hodnota této položky odkazuje na správný DLL rozhraní IDE.  
  
 Správa zdrojového kódu modul plug-in musí podporovat obou směrech nalezení knihovny DLL a v důsledku toho nastavte ProviderRegKey, přepsal jakékoli předchozí nastavení. Je důležité se musí sám přidat do seznamu InstalledSccProviders takže uživatel může vybrat, které modul plug-in správy zdroje používat.  
  
> [!NOTE]
>  Protože se používá klíč HKEY_LOCAL_MACHINE, modul plug-in správy jen jednu zdrojovou lze registrovat jako výchozí zdroj ovládacího prvku modulu plug-in v daném počítači (však [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] umožňuje uživatelům zjistit, které modul plug-in správy zdroje ve skutečnosti používají pro konkrétní řešení). Během procesu instalace zkontrolujte, pokud je již nastaven zdrojového kódu, který je modul plug-in; Pokud ano, požádejte uživatele, zda chcete nastavit nové zdrojového kódu modul plug-in instaluje jako výchozí. Během odinstalace neodebírejte další podklíče registru, které jsou společné pro všechny zdroje řízení moduly plug-in v HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider; Odeberte pouze vaše konkrétní podklíč SCC.  
  
## <a name="how-the-ide-detects-version-1213-support"></a>Jak IDE zjistí verze 1.2 nebo 1.3 podpory  
 Jak nemá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] detekci, jestli je modul plug-in podporuje rozhraní API modulu Plugin zdroj ovládacího prvku verze 1.2 a 1.3 funkce? Deklarovat pokročilé funkce, musí implementovat modul plug-in správy zdroje odpovídající funkce.  
  
 První, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kontroluje hodnoty vrácené volání [SccGetVersion](../../extensibility/sccgetversion-function.md). Ho musí být větší než nebo rovna hodnotě 1.2.  
  
 Dále [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Určuje, jestli konkrétní nová funkce podporuje `lpSccCaps` argument na [SccInitialize](../../extensibility/sccinitialize-function.md).  
  
 Pokud jsou obě tyto podmínky splněny, je možné volat podporované ve verzi 1.2 a 1.3 nové funkce.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)