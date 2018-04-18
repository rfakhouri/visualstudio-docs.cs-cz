---
title: Registrace a výběr (Zdroj ovládacího prvku VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, source control packages
- source control packages, registration
ms.assetid: 7d21fe48-489a-4f55-acb5-73da64c4e155
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d7bcdb8f930430ac00335777e2c088ce52a34bb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registration-and-selection-source-control-vspackage"></a>Registrace a výběr (Zdroj ovládacího prvku VSPackage)
Správa zdrojového kódu VSPackage musí být zaregistrován ke zveřejnění jeho [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Není-li více než jeden zdroj prvek VSPackage registrován, kterého uživatel může vybrat které VSPackage načíst v příslušnou dobu. V tématu [VSPackages](../../extensibility/internals/vspackages.md) další podrobnosti o VSPackages a postup jejich registrace.  
  
## <a name="registering-a-source-control-package"></a>Registrace balíčku zdroj ovládacího prvku  
 Zdrojový balíček ovládací prvek je zaregistrován tak, aby [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí najdete ho a dotazů pro jeho podporované funkce. Toto je v souladu s zpoždění načítání schématu, ve kterém se vytvoří instance balíčku jenom v případě, že jeho funkce nebo příkazy jsou vyžadována nebo jsou explicitně požadována.  
  
 VSPackages umístit informace v klíči registru specifické pro verzi, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*X.Y*, kde *X* je hlavní číslo verze a *Y* je číslo podverze. Tento postup umožňuje podporovat vedle sebe instalaci více verzí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Uživatelské rozhraní (UI) a také zdrojového kódu VSPackages podporuje výběru některé z těchto více nainstalované zdroj ovládacího prvku moduly plug-in (prostřednictvím zdrojový balíček ovládací adaptéru). Může existovat jenom jeden modul plug-in správy active zdroje nebo VSPackage najednou. Ale jak je popsáno níže, rozhraní IDE umožňuje přepínání mezi zdroj ovládacího prvku zásuvné moduly a VSPackages prostřednictvím automatického řešení na základě balíčku odkládací mechanismus. Existují některé požadavky ze strany zdrojového kódu VSPackage povolit tento mechanismus výběru.  
  
### <a name="registry-entries"></a>Položky registru  
 Zdroj balíčku řízení potřebuje tři soukromé identifikátory GUID:  
  
-   GUID balíčku: Toto je hlavní identifikátor GUID pro balíček, který obsahuje implementaci ovládacího prvku zdroje (nazývané ID_Package v této části).  
  
-   Správa zdrojového kódu identifikátor GUID: Toto je identifikátor GUID pro zdrojového kódu VSPackage používá k registraci pomocí Visual Studio zdroj ovládacího prvku se zakázaným inzerováním a slouží taky jako kontext uživatelského rozhraní příkazů GUID. Službu Řízení zdroj GUID je zaregistrovaný pod identifikátor GUID zdrojového kódu. V příkladu se nazývá identifikátor GUID zdrojového kódu ID_SccProvider.  
  
-   Zdroj služby Řízení identifikátor GUID: Jedná se o privátní službu GUID sada Visual Studio (nazývané SID_SccPkgService v této části). Kromě toho musí zdrojový balíček řízení definovat další identifikátory GUID pro VSPackages, nástroj windows, a tak dále.  
  
 Následující položky registru je nutné provést podle VSPackage Správa zdrojového kódu:  
  
|Název klíče|Položky|  
|--------------|-------------|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\`|(výchozí) = rg_sz: {ID_SccProvider}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\`|(výchozí) = rg_sz:\<popisný název balíčku ><br /><br /> Služba = rg_sz: {SID_SccPkgService}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\               Name\`|(výchozí) = rg_sz: #\<ID prostředku pro lokalizovaný název ><br /><br /> Balíček = rg_sz: {ID_Package}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SolutionPersistence\             <PackageName>\`<br /><br /> (Všimněte si, že název klíče `SourceCodeControl`, je již využíván [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a není k dispozici jako volba pro \<název balíčku >.)|(výchozí) = rg_sz: {ID_Package}|  
  
## <a name="selecting-a-source-control-package"></a>Výběr zdroje balíčku ovládací prvek  
 Několik založené na rozhraní API modulu Plugin zdroj ovládacího prvku moduly plug-in a ovládací prvek VSPackages může souběžně zaregistrovat zdroje. Proces výběru zdrojového kódu modul plug-in nebo VSPackage musíte zajistit, aby [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] načte modul plug-in nebo VSPackage v příslušnou dobu a můžete odložit načítání nepotřebné součásti, dokud jsou povinné. Kromě toho [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] musíte odebrat všechny uživatelského rozhraní od jiných neaktivní VSPackages, včetně položek nabídky, dialogová okna a panely nástrojů a zobrazit uživatelské rozhraní pro aktivní VSPackage.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Správa zdrojového kódu VSPackage načte, když se provádí některého z následujících operací:  
  
-   (Pokud je řešení ve správě zdrojového kódu), je řešení otevřené.  
  
     Po otevření řešení nebo projektu ve správě zdrojového prostředí IDE způsobí, že správa zdrojového kódu VSPackage, který byl navržený pro toto řešení, které mají být načtena.  
  
-   Všechny příkazy v nabídce Správa zdrojového kódu VSPackage provedení.  
  
 Správa zdrojového kódu VSPackage by se měly načíst všechny součásti, které je nutné pouze v případě, že se ve skutečnosti má být použit (jinak se označuje jako zpožděné načítání).  
  
### <a name="automatic-solution-based-vspackage-swapping"></a>Vzájemná záměna automatické VSPackage založené na řešení  
 Ručně odkládacího souboru zdrojového kódu VSPackages prostřednictvím [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **možnosti** dialogového okna **správy zdrojového kódu** kategorie. Automatické řešení na základě balíčku odkládací znamená, že zdrojový balíček ovládací prvek, který určil pro konkrétní řešení je automaticky nastaven na hodnotu aktivní, když toto řešení je otevřen. Každý balíček zdroj ovládacího prvku by měla implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zpracovává přepínat mezi oba zdroje řízení moduly plug-in (implementace rozhraní API ovládacího prvku Plug-in zdroje) a ovládací prvek VSPackages zdroje.  
  
 Zdrojový balíček ovládací adaptéru slouží k přepnout na všechny založené na rozhraní API modulu Plugin řízení zdroj modulu plug-in. Proces probíhá přepínání na zprostředkující zdrojový balíček ovládací adaptéru a určení, které modul plug-in správy zdroje musí být nastavena na aktivní nebo neaktivní je pro uživatele transparentní. Balíček adaptér je aktivní, vždy když je aktivní žádné modulu plug-in zdrojového kódu. Přepínání mezi dvěma zdroj ovládacího prvku moduly plug-in činí jednoduše načítání a uvolňování knihovnu DLL modulu plug-in. Přepnutí do zdrojového kódu VSPackage, ale zahrnuje interakci s IDE načíst odpovídající VSPackage.  
  
 Správa zdrojového kódu VSPackage je volána, když je řešení otevřené a klíč registru pro VSPackage je v souboru řešení. Po otevření řešení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hodnotu registru vyhledá a načte odpovídající zdrojového kódu VSPackage. Všechny zdrojového kódu VSPackages musí mít položky registru popsané výše. Řešení, které je ve správě zdrojů je označena jako bylo možné přidružit konkrétní zdrojového kódu VSPackage. Ovládací prvek VSPackages musí implementovat zdroje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> povolit automatické založené na řešení VSPackage odkládací.  
  
### <a name="visual-studio-ui-for-package-selection-and-switching"></a>Visual Studio uživatelského rozhraní pro výběr balíčku a přepínání  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje uživatelské rozhraní pro řízení zdrojů VSPackage a modul plug-in výběr v **možnosti** dialogového okna **správy zdrojového kódu** kategorie. Umožňuje uživateli vybrat modul plug-in správy active zdroje nebo VSPackage. Rozevírací seznam obsahuje:  
  
-   Všechny nainstalované balíky pro řízení zdrojového  
  
-   Nainstalovány všechny moduly plug-in programu zdroj ovládacího prvku  
  
-   "Žádný" možnost, která zakáže zdrojového kódu  
  
 Pouze uživatelské rozhraní pro řízení volba aktivní zdrojová je viditelný. Výběr VSPackage skryje uživatelské rozhraní pro předchozí VSPackage a zobrazuje uživatelské rozhraní pro novým. Aktivní VSPackage je vybrané na jednotlivých uživatelů. Pokud má uživatel více kopií [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] otevřete souběžně, potenciálně každé z nich můžete použít různé active VSPackage. Pokud přihlášení víc uživatelů na stejný počítač, každý uživatel může mít samostatné instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] otevřít, každý s jinou active VSPackage. Když více instancí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] jsou uzavřené uživatelem, Správa zdrojového kódu VSPackage, který byl aktivní pro poslední otevřete řešení změní výchozí zdrojového kódu VSPackage nastavit aktivní na restartování.  
  
 Na rozdíl od předchozích verzí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], se už o restartování IDE jediný způsob, jak přepnout VSPackages zdrojového kódu. Výběr VSPackage je automatické. Přepínání balíčky vyžaduje oprávnění uživatele systému Windows (není správce nebo Power User).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>   
 [Funkce](../../extensibility/internals/source-control-vspackage-features.md)   
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)