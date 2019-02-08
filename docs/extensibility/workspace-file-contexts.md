---
title: Kontexty souborů pracovní prostor v sadě Visual Studio | Dokumentace Microsoftu
ms.date: 02/21/2018
ms.topic: conceptual
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 36f986db6f2c7b483b46060e1f514acc8dd9e758
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939187"
---
# <a name="workspace-file-contexts"></a>Kontexty souborů pracovního prostoru

Všechny přehledy o [otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) "kontextu zprostředkovatelé souborů", které implementují vytvářených pracovních prostorů <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider> rozhraní. Tato rozšíření můžou vyhledávat vzory ve složkách nebo souborů, přečtěte si MSBuild – soubory a soubory pravidel, detekovat závislosti balíčků, atd. aby bylo možné shromažďovat informace, že které potřebují k definování kontextu souboru. Kontext souboru sám o sobě neprovede žádnou akci, ale místo toho poskytuje data, která jinou příponu pak dají dále rozvíjet.

Každý <xref:Microsoft.VisualStudio.Workspace.FileContext> má `Guid` s ním spojená, který identifikuje typ dat se má u sebe. Tento pracovní prostor využívá `Guid` později zarovnali do vzájemně odpovídající ho s rozšířeními, která využívají data prostřednictvím <xref:Microsoft.VisualStudio.Workspace.FileContext.Context> vlastnost. Poskytovatel kontextu souboru se exportuje s metadaty, který identifikuje soubor kontext `Guid`s vytvořit data.

Po definování kontextu souboru lze přidružit libovolný počet soubory nebo složky v pracovním prostoru. Daný soubor nebo složku může být spojen s libovolný počet kontextů souboru. Je relace m: m.

Nejběžnější scénáře pro kontexty souborů se vztahují k sestavování, ladění a jazykových služeb. Další informace najdete v tématu další témata související s tyto scénáře.

## <a name="file-context-lifecycle"></a>Životní cyklus kontextu souboru

Časově omezené `FileContext` jsou nedeterministické. V každém okamžiku komponentu asynchronně požádat některé množiny typů kontextu. Bude se dotazovat na zprostředkovatele, které podporují určité dílčí sady typů kontextu požadavku. `IWorkspace` Instance funguje jako střední man mezi příjemců a prostřednictvím poskytovatelů <xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A> metody. Spotřebitelé můžou požádat o kontext a provedení některých krátkodobé akce na základě kontextu, zatímco jiné můžou požádat o kontext a udržovat dlouhodobá odkaz.

Změny může dojít k souborům, které způsobují kontextu souboru k začnou být zastaralé. Zprostředkovatel může vyvolat událost v `FileContext` oznámit příjemci aktualizací. Například pokud kontext sestavení je k dispozici pro některý soubor ale o změnu na disku zruší platnost tohoto kontextu, poté původce můžete je vyvolat události. Kterýchkoli stále odkazuje, který `FileContext` můžete pak requery nový `FileContext`.

>[!NOTE]
>Neexistuje žádný model push pro uživatele. Příjemci nedostanou poskytovatele nové `FileContext` po jejich požadavku.

## <a name="expensive-file-context-computations"></a>Místní výpočty nákladné souboru

Obsah souboru čtení z disku může být náročné, zejména v případě, že zprostředkovatel potřebuje k vyřešení vztahu mezi soubory. Například poskytovatel může dotazovat některé zdrojový soubor souboru kontextu, ale kontext souboru je závislá na metadata ze souboru projektu. Parsování souboru projektu nebo vyhodnocení pomocí nástroje MSBuild je nákladný. Místo toho můžete exportovat rozšíření `IFileScanner` vytvořit `FileDataValue` dat během indexování pracovního prostoru. Teď když se zobrazí výzva pro kontexty souborů `IFileContextProvider` rychle vyhledávat indexovaná data. Další informace o indexování, najdete v článku [pracovní prostor indexování](workspace-indexing.md) tématu.

>[!WARNING]
>Buďte opatrní dalšími způsoby vaše `FileContext` může být náročné na výpočetní. Některé interakce uživatelského rozhraní jsou synchronní a využívají k velkému počtu `FileContext` požadavky. Mezi příklady patří otevřením karty editoru a otevírání **Průzkumníka řešení** kontextové nabídky. Tyto akce provést mnoho kontext sestavení zadejte požadavky.

## <a name="file-context-related-apis"></a>Rozhraní API související s místní soubor

- <xref:Microsoft.VisualStudio.Workspace.FileContext> obsahuje data a metadata.
- <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider> a <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider`1> vytvořte místní soubor.
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextProviderAttribute> Exportuje zprostředkovatele kontextu souborů.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A> umožňuje uživatelům získat kontexty souborů.
- <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes> Definuje typy kontextu sestavení, které bude využívat funkce Otevřít složku.

## <a name="file-context-actions"></a>Akce kontextu souboru

Zatímco `FileContext` sám o sobě představuje pouze data o některé soubory <xref:Microsoft.VisualStudio.Workspace.IFileContextAction> je způsob, jak express a reagovat na těchto datech. `IFileContextAction` je flexibilní jeho využití. Dva z jeho nejběžnější případy jsou sestavování a ladění.

## <a name="reporting-progress"></a>Vykazování průběhu

<xref:Microsoft.VisualStudio.Workspace.IFileContextActionBase.ExecuteAsync%2A> Metodě je předána `IProgress<IFileContextActionProgressUpdate>`, ale nepoužívali argument typu. `IFileContextActionProgressUpdate` je prázdné rozhraní a vyvolání `IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)` může vyvolat `NotImplementedException`. Místo toho `IFileContextAction` musíte přetypovat argument na jiný typ podle potřeby pro scénář.

Informace o typech získáte ho od sady Visual Studio najdete v dokumentaci příslušné scénář.

## <a name="file-context-action-related-apis"></a>Rozhraní API související s akce kontextu souboru

- <xref:Microsoft.VisualStudio.Workspace.IFileContextAction> provede některé rysy chování na základě `FileContext`.
- <xref:Microsoft.VisualStudio.Workspace.IFileContextActionProvider> vytváří instance `IFileContextAction`.
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextActionProviderAttribute> Exportuje typ `IWorkspaceProviderFactory<IFileContextActionProvider>`.

## <a name="file-watching"></a>Sledování souboru

Pracovní prostor naslouchá oznámení o změně souborů a poskytuje <xref:Microsoft.VisualStudio.Workspace.IFileWatcherService> prostřednictvím <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>. Soubory odpovídající nastavení "ExcludedItems" nevytvoří soubor oznámení události. Prahová hodnota mezi událostmi se používá pro zjednodušení oznámení a snížení duplicitní. Když budete potřebovat reagovat na změnu souboru, jste měli k odběru této služby.

>[!TIP]
>Pracovní prostor [indexovací službou](workspace-indexing.md) se přihlásí k odběru událostí souborů ve výchozím nastavení. Soubor dodatků a změn způsobí, že příslušné `IFileScanner`s události mají být vyvolány pro nová data pro tento soubor. Odstranění souboru se odeberou indexovaná data. Není nutné k odběru vaše `IFileScanner` do souboru sledovacího procesu služby.

## <a name="next-steps"></a>Další kroky

* [Indexování](workspace-indexing.md) – pracovní prostor indexování shromažďuje a opakuje informace o pracovním prostoru.
* [Pracovní prostory](workspaces.md) – projděte si koncepty pracovního prostoru a nastavení úložiště.
