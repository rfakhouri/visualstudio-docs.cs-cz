---
title: Správa načítání projektů v řešení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a383096d164f1b08e2411a7bc808e96f8a6262e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60061304"
---
# <a name="manage-project-loading-in-a-solution"></a>Správa načítání projektů v řešení
Řešení sady Visual Studio může obsahovat velký počet projektů. Výchozí chování sady Visual Studio je načíst všechny projekty v řešení v době, kdy je otevřené řešení a nikoli do povolí uživateli přístup žádným z projektů, dokud všechny z nich dokončení načítání. Při procesu načítání projektu bude trvat více než dvě minuty, se zobrazí indikátor průběhu zobrazující počet projekty a celkovém počtu projektů. Uživatel může při práci v řešení s více projekty uvolnění projektů, ale tento postup má i určité nevýhody: jako součást příkazu znovu sestavit řešení nejsou sestaveny uvolněné projekty a popisy technologie IntelliSense typů a členů uzavřený projekty se nezobrazí.

 Vývojářům můžete snížit dobu načítání řešení a spravovat chování načítání tím, že vytvoříte načtení řešení správce projektu. Správci řešení zatížení můžete Ujistěte se, že projekty načetly před spuštěním sestavení na pozadí, zpoždění načítání na pozadí, dokud nebudou dokončeny ostatní úlohy na pozadí a provádět další úkoly při správě zatížení projektu.

## <a name="create-a-solution-load-manager"></a>Vytvoření správce načtení řešení
 Vývojáři mohou vytvářet načtení řešení Správce implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> a sady Visual Studio, že správce zatížení řešení je aktivní.

### <a name="activate-a-solution-load-manager"></a>Aktivovat správce zatížení řešení
 Visual Studio umožňuje pouze jeden správce zatížení řešení v daném okamžiku, proto musíte poradit sady Visual Studio, pokud chcete aktivovat vaše načtení řešení správce. Pokud později při aktivaci druhý správce zatížení řešení správce zatížení řešení bude odpojen.

 Musíte získat <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> služby a nastavení [__VSPROPID4. VSPROPID_ActiveSolutionLoadManager](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_ActiveSolutionLoadManager>) vlastnost:

```csharp
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;
object objLoadMgr = this;   //the class that implements IVsSolutionManager
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);
```

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Metoda je volána, když probíhá vypínání aplikace Visual Studio nebo když se jiný balíček má převzetí jako správce zatížení aktivního řešení voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> s [__VSPROPID4. VSPROPID_ActiveSolutionLoadManager](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_ActiveSolutionLoadManager>) vlastnost.

#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>Strategie pro různé druhy řešení načíst správce
 Správci zatížení řešení můžete implementovat různými způsoby v závislosti na typech řešení, které jsou určené pro správu.

 Pokud se správce zatížení řešení pro správu obecně načítání řešení, se dá implementovat jako součást sady VSPackage. Balíček musí být nastavená na autoload tak, že přidáte <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> na VSPackage s hodnotou <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>. Správci řešení zatížení můžete v aktivovat <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metody.

> [!NOTE]
>  Další informace o balíčcích autoloading najdete v tématu [načítání rozšíření VSPackages](../extensibility/loading-vspackages.md).

 Vzhledem k tomu, že Visual Studio rozpozná pouze poslední řešení zatížení správce aktivaci, by měl obecné řešení zatížení správci vždy zjistit, zda je před aktivací sami stávající správce zatížení. Pokud volání `GetProperty()` řešení služby pro [__VSPROPID4. VSPROPID_ActiveSolutionLoadManager](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_ActiveSolutionLoadManager>) vrátí `null`, neexistuje žádný správce zatížení aktivního řešení. Pokud nevrací hodnotu null, zkontrolujte, zda je objekt stejný jako správce zatížení vašeho řešení.

 Pokud se správce zatížení řešení pro správu pouze několik typů řešení, sady VSPackage mohou přihlásit k odběru událostí načítání řešení (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>) a použijte obslužnou rutinu události pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> aktivovat správce zatížení řešení.

 Pokud se správce zatížení řešení pro správu pouze konkrétní řešení, informace o aktivaci můžete nastavit jako trvalý soubor řešení v rámci voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> pro části před řešení.

 Konkrétní řešení zatížení Správce by měl deaktivovat sebe sama v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> obslužná rutina události, aby nebyla v konfliktu s ostatními správci načtení řešení.

 Pokud potřebujete správce zatížení řešení pouze k uchování globálních projektu zatížení vlastnosti (například vlastnosti nastavené u stránky Možnosti), můžete si aktivovat správce zatížení řešení v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> obslužná rutina události, zachovat nastavení klikněte v okně vlastností řešení Deaktivujte správce zatížení řešení.

## <a name="handle-solution-load-events"></a>Zpracování událostí načtení řešení
 Chcete-li přihlásit k odběru řešení zatížení události, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> při aktivaci správce zatížení vašeho řešení. Pokud se rozhodnete implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, můžete reagovat na události, které se vztahují k jinému projektu načítání vlastností.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>: Tato událost je aktivována před otevřením řešení.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>: Tato událost je aktivována po řešení, je zcela načten, ale před pozadí začne znovu načíst projekt.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>: Tato událost je aktivována po načtení řešení je zpočátku plně, jestli správce zatížení řešení. Také aktivuje po načtení na pozadí nebo vyžádání načíst pokaždé, když se stane řešení plně načteno. Ve stejnou dobu <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> se znovu aktivuje.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>: Tato událost je aktivována před načtením projektu (nebo projektů). Ujistěte se, že ostatní procesy na pozadí se dokončila předtím, než se načtou projekty, nastavte `pfShouldDelayLoadToNextIdle` k **true**.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>: Tato událost je aktivována, když dávku projekty se jej načíst. Pokud `fIsBackgroundIdleBatch` má hodnotu true, projekty, které se mají být načteny na pozadí; Pokud `fIsBackgroundIdleBatch` má hodnotu false, projekty, které mají být načteny synchronně jako výsledek požadavku na uživatele, například pokud je uživatel rozbalí čekajícího projektu v Průzkumníku řešení. Dokáže zpracovat tuto událost nákladné práci, v opačném případě by bylo potřeba udělat v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>: Tato událost je aktivována po načtení služby batch projektů.

## <a name="detect-and-manage-solution-and-project-loading"></a>Zjišťovat a spravovat řešení a načítání projektů
 Aby bylo možné zjistit stav načtení projekty a řešení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> s použitím následujících hodnot:

- [__VSPROPID4. VSPROPID_IsSolutionFullyLoaded](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_IsSolutionFullyLoaded>): `var` vrátí `true` Pokud řešení a všechny jeho projekty jsou načteny, jinak `false`.

- [__VSPROPID4. VSPROPID_IsInBackgroundIdleLoadProjectBatch](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_IsInBackgroundIdleLoadProjectBatch>): `var` vrátí `true` Pokud dávku projekty aktuálně načítání na pozadí, v opačném případě `false`.

- [__VSPROPID4. VSPROPID_IsInSyncDemandLoadProjectBatch](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4.VSPROPID_IsInSyncDemandLoadProjectBatch>): `var` vrátí `true` Pokud dávku projekty se aktuálně načítá synchronně jako výsledek příkazu uživatele nebo jiné explicitní zatížení, jinak `false`.

- [__VSPROPID2. VSPROPID_IsSolutionClosing](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2.VSPROPID_IsSolutionClosing>): `var` vrátí `true` Pokud řešení aktuálně dochází k uzavření, jinak `false`.

- [__VSPROPID. VSPROPID_IsSolutionOpening](<xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID.VSPROPID_IsSolutionOpening>): `var` vrátí `true` Pokud řešení je právě otevřen, v opačném případě `false`.

Můžete také zajistit, že projekty a řešení jsou načteny voláním jedné z následujících metod:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: volání této metody vynutí projekty v řešení se načíst dříve, než metoda vrátí.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>: volání této metody vynutí projekty v `guidProject` načíst dříve, než metoda vrátí.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>: volání této metody vynutí projekt v `guidProjectID` načíst dříve, než metoda vrátí.
