---
title: "Správa projektu načítání v řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2dbbb8ddcf574f2e3db81ce63db257e21ff88839
ms.sourcegitcommit: a80e7ef2f0a0f6d906a44f4d696aeb208bc1ad70
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2018
---
# <a name="managing-project-loading-in-a-solution"></a>Správa načítání projektu v řešení
Řešení sady Visual Studio může obsahovat velké množství projekty. Výchozí chování sady Visual Studio je načíst všechny projekty v řešení v době, kdy je řešení otevřené a nechcete povolit uživateli přístup k žádným z projektů všechny z nich nedokončili načítání. Při procesu načítání projektu bude poslední více než dvě minuty, se zobrazí indikátor průběhu zobrazující počet projekty načíst a celkový počet projekty. Uživatel může mít za následek uvolnění projekty při práci s řešení s více projekty, ale tento postup má některé nevýhody: odpojen projekty nejsou vytvořené jako součást příkazu znovu sestavit řešení a popisy IntelliSense typů a členů uzavřený projekty nejsou zobrazeny.  
  
 Vývojáři můžou snížit zatížení doby řešení a spravovat projektu načítání chování vytvořením řešení zatížení správce. Správce zatížení řešení můžete Ujistěte se, zda jsou načteny projekty před zahájením pozadí sestavení, zpoždění pozadí načítání, dokud nebudou dokončeny jiné úlohy na pozadí a provádět další úlohy správy zatížení projektu.  
  
## <a name="creating-a-solution-load-manager"></a>Vytváření řešení zatížení manager  
 Vývojáři můžou vytvářet řešení zatížení manager implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> a poradenství Visual Studio, že správce zatížení řešení je aktivní.  
  
#### <a name="activating-a-solution-load-manager"></a>Aktivace správce zatížení řešení  
 Visual Studio umožňuje pouze jeden správce zatížení řešení v daném okamžiku, musíte poradit Visual Studio, pokud chcete aktivovat zatížení řešení správce. Pokud později na aktivaci druhý správce zatížení řešení bude odpojen správce zatížení vašeho řešení.  
  
 Musíte získat <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> služby a nastavte <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vlastnost:  
  
```csharp  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;  
object objLoadMgr = this;   //the class that implements IVsSolutionManager  
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Metoda je volána, když Visual Studio se právě vypíná nebo když se jiný balíček trvá jako správce zatížení aktivním řešení voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> s <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vlastnost.  
  
#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>Strategie pro různé druhy správce zatížení řešení  
 Správci zatížení řešení můžete implementovat různými způsoby v závislosti na typech řešení, která jsou určená ke správě.  
  
 Pokud správce zatížení řešení slouží ke správě řešení načítání obecně, se dá implementovat jako součást VSPackage. Balíček musí být nastavena na autoload přidáním <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> na VSPackage s hodnotou <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>. Správce zatížení řešení můžete za aktivuje <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
> [!NOTE]
>  Další informace o balíčcích autoloading najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md).  
  
 Vzhledem k tomu, že Visual Studio rozpozná pouze poslední řešení zatížení správce chcete aktivovat, musí správce zatížení obecné řešení vždy zjistí, zda je před aktivací sami existující správce zatížení. Pokud ve službě řešení pro volání metody GetProperty() <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> vrátí `null`, neexistuje žádný správce zatížení aktivním řešení. Pokud není vrátit hodnotu null, zkontrolujte, zda je objekt stejný jako správce zatížení vašeho řešení.  
  
 Pokud správce zatížení řešení slouží ke správě pouze několik typů řešení, VSPackage mohou přihlásit k odběru událostí načítání řešení (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>) a použijte obslužnou rutinu události pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> aktivovat správce zatížení řešení.  
  
 Pokud správce zatížení řešení slouží ke správě pouze konkrétní řešení, informace o aktivaci lze zachovat jako část souboru, řešení voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> pro oddíl předběžné řešení.  
  
 Správci zatížení specifického řešení by měl deaktivovat sami v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> obslužné rutiny události, aby se v konfliktu s jiným správcům zatížení řešení.  
  
 Pokud potřebujete řešení zatížení správce pouze pro udržení zatížení vlastnosti globální projektu (například vlastnosti nastavit na stránce Možnosti), můžete si aktivovat správce zatížení řešení v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> obslužné rutiny události, zachovat nastavení pak ve vlastnostech řešení Deaktivujte správce zatížení řešení.  
  
## <a name="handling-solution-load-events"></a>Zpracování událostí zatížení řešení  
 K odběru událostí načítání řešení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> Když aktivujete správce zatížení vašeho řešení. Pokud implementujete <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, můžete reakce na události, které se vztahují k načtení vlastnosti jiný projekt.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>: Tato událost je aktivována, před otevřením řešení.
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>: Tato událost je aktivována po řešení, které je zcela načten, ale před pozadí projektu načítání začne počítat od začátku.
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>: Tato událost je aktivována po začátku plně načtení řešení, zda je manažera zatížení řešení. Také je aktivována, po načtení pozadí nebo vyžádání načíst vždy, když se stane úplným načtením řešení. Ve stejnou dobu <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> opětovné aktivaci.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>: Tato událost je aktivována před načtením projektu (nebo projekty). Chcete-li zajistit, že jiné procesy na pozadí jsou dokončeny před projektů jsou načteny, nastavte `pfShouldDelayLoadToNextIdle` k **true**.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>: Tato událost je aktivována, jestliže dávky projekty je možné načíst. Pokud `fIsBackgroundIdleBatch` má hodnotu true, projektů se mají načíst na pozadí; Pokud `fIsBackgroundIdleBatch` je nastavena hodnota false, projekty, které mají být načteny synchronně jako výsledek požadavku na uživatele, například pokud uživatel rozšíří čeká na projekt v Průzkumníku řešení. Dokáže zpracovat Tato událost při práci se náročná, v opačném případě by bylo potřeba provést <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>: Tato událost je aktivována po dávky projekty se načetl.  
  
## <a name="detecting-and-managing-solution-and-project-loading"></a>Zjišťování a Správa řešení a načítání projektu  
 Aby bylo možné zjistit stav zatížení projekty a řešení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> s následujícími hodnotami:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud všechny své projekty a řešení se načtou, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud dávky projekty aktuálně načítání na pozadí, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` vrátí `true` Pokud dávky projekty se právě načítá synchronně v důsledku příkaz uživatele nebo jiných explicitní zatížení, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>: `var` vrátí `true` Pokud řešení aktuálně dochází k uzavření, jinak `false`.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>: `var` vrátí `true` Jestliže řešení je aktuálně otevíráte, jinak `false`.  
  
 Můžete také zajistit, že jsou načtená projekty a řešení při volání jedné z následujících metod:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: voláním této metody vynutí projekty v řešení pro načtení předtím, než se vrátí tato metoda hodnotu.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>: voláním této metody vynutí projekty v `guidProject` načíst než metoda vrátí.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>: voláním této metody vynutí na projekt v `guidProjectID` načíst než metoda vrátí.  
