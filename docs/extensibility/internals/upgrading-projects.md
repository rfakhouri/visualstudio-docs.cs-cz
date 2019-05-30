---
title: Upgrade projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- upgrading VSPackages
- upgrading applications, strategies
- VSPackages, upgrade support
ms.assetid: e01cb44a-8105-4cf4-8223-dfae65f8597a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6a9e5b73315d8332c71e0fb7ddc3c6c1df041c3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344677"
---
# <a name="upgrading-projects"></a>Upgrade projektů

Změny modelu projektu z jedné verze nástroje Visual Studio na další mohou vyžadovat, že projekty a řešení upgradovat tak, aby mohli spouštět na novější verzi. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Poskytuje rozhraní, které lze použít k implementaci podporu upgradu v svoje vlastní projekty.

## <a name="upgrade-strategies"></a>Strategie upgradu

Implementace systému projektu pro podporu upgradu, musíte definovat a implementovat upgradu strategie. Při určování strategie, můžete pro podporu side-by-side (SxS) zálohování nebo zálohování kopírováním.

- Zálohování SxS znamená, že projekt zkopíruje pouze soubory, které potřebují upgrade na místě, přidání vhodný název příponu souboru, například "old".

- Zálohování kopírováním znamená, že projekt zkopíruje všechny položky projektu do uživatelem zadaného umístění zálohy. Relevantní soubory do původního umístění projektu jsou potom upgradovat.

## <a name="how-upgrade-works"></a>Jak upgradovat funguje

Při otevření řešení vytvořené v dřívější verzi sady Visual Studio v novější verzi, rozhraní IDE zkontroluje soubor řešení Chcete-li zjistit, jestli je potřeba upgradovat. Je-li upgrade vyžadováno, **Průvodce upgradem** se automaticky spustí, aby vás uživatel provede procesem.

Při řešení potřebuje upgrade, vyžádá si každý projektu pro vytváření pro své strategie upgradu. Strategie určí, zda objekt pro vytváření projektů podporuje zálohování kopírováním nebo SxS zálohování. Informace odeslány **Průvodce upgradem**, který shromažďuje informace potřebné pro zálohování a zobrazí příslušné možnosti pro uživatele.

### <a name="multi-project-solutions"></a>Řešení vícenásobného projektu

Pokud řešení obsahuje více projektů a upgradu strategie liší, jako když projektu jazyka C++, který podporuje pouze SxS zálohování, webový projekt, který podporuje jenom zálohování kopírováním objektů pro vytváření projektů musí si vyjednat strategie upgradu.

Každý projekt pro vytváření pro dotazy řešení <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>. Poté zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject_CheckOnly%2A> zobrazíte potřebujete globální projektových souborů, upgrade a na zjištění podporované upgradu strategie. **Průvodce upgradem** následně vyvolány.

Po dokončení průvodce, uživatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> je volána na objektu pro vytváření každý projekt skutečné upgradu. Pro usnadnění zálohování, IVsProjectUpgradeViaFactory metody poskytují <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> služby protokolovat podrobnosti o procesu upgradu. Tato služba nejde udržovat v mezipaměti.

Po aktualizaci všechny relevantní soubory globální, každý objekt pro vytváření projektu můžete vytvořit instanci projektu. Implementace projektu musí podporovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> Metoda je volána poté upgradovat všechny položky příslušného projektu.

> [!NOTE]
> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> Metoda neposkytuje SVsUpgradeLogger službu. Tato služba lze získat voláním <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>.

## <a name="best-practices"></a>Doporučené postupy

Použití <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> služby zkontrolujte, jestli můžete upravit soubor začnete upravovat a můžete ji uložit před uložením. To vám pomůže zálohování a upgradu implementace zpracovat soubory projektu pod správou zdrojových kódů, soubory s dostatečná oprávnění a tak dále.

Použití <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> služby během všech fází zálohování a upgradovat na poskytují informace o úspěchu nebo selhání procesu upgradu.

Další informace o zálohování a upgrade projektů naleznete v tématu komentáře IVsProjectUpgrade v vsshell2.idl.

## <a name="upgrading-custom-projects"></a> Upgrade vlastních projektů

Pokud změníte informací uchovávaných v souboru projektu mezi různými verzemi sady Visual Studio, produktu, je nutné pro podporu upgradu váš soubor projektu ze staré na novou verzi. Pro podporu upgradu, která umožňuje vás k účasti **Průvodce převodu Visual Studio**, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> rozhraní. Toto rozhraní obsahuje pouze mechanismus k dispozici pro upgrade kopírování. Upgrade projektu se stane, jako součást řešení otevře. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> Rozhraní je implementováno objekt pro vytváření projektu, nebo by měl být dosažitelný alespoň z objekt pro vytváření projektu.

Staré mechanismus, který používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> rozhraní je stále podporovány, ale koncepčně upgraduje systém projektu jako součást po otevření projektu. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> Rozhraní je tedy volána prostředí sady Visual Studio, i když <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> je volána nebo implementované rozhraní. Tento přístup umožňuje používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> implementovat kopii projektu pouze části upgradu a delegujte zbývající práce, která musí provést na místě (případně na nové umístění) pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> rozhraní.

Pro ukázková implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>, naleznete v tématu [VSSDK ukázky](https://aka.ms/vs2015sdksamples).

Následujících scénářích vznikají s upgradem projektu:

- Pokud je soubor formátu novější, než může zajistit projektu, se musí vrátit chybu s informacemi o tom to. Předpokladem je, že starší verzi produktu obsahuje kód pro kontrolu verze.

- Pokud <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP> zadán příznak v <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> metody upgradu bude možné implementovat jako upgrade v místě před počáteční projekt.

- Pokud <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_COPYBACKUP> zadán příznak v <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> metoda, upgrade je implementovaný jako upgradu na kopii.

- Pokud <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> zadán příznak v <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> volání, pak uživatel je vyzván prostředím upgrade souboru projektu jako místní upgrade, po otevření projektu. Například prostředí se zobrazí výzva k upgradu, když uživatel otevře starší verzi řešení.

- Pokud <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> příznak není zadán v <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> volání, pak musí požádat uživatele upgrade souboru projektu.

     Tady je ukázková zpráva upgradu příkazový řádek:

     "Projekt '%1' byl vytvořen starší verzí sady Visual Studio. Když jej otevřete s touto verzí sady Visual Studio, nemusí být možné otevřít ve starších verzích sady Visual Studio. Opravdu chcete pokračovat a otevřít tento projekt?"

### <a name="to-implement-ivsprojectupgradeviafactory"></a>K implementaci IVsProjectUpgradeViaFactory

1. Implementovat metodu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> rozhraní speciálně <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> metodu ve vaší implementaci objekt pro vytváření projektu, nebo učiňte implementace volat z vašeho projektu implementace objektu factory.

2. Pokud chcete provést místní upgrade jako součást řešení, otevření, zadat příznak <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP> jako `VSPUVF_FLAGS` parametr ve vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> implementace.

3. Pokud chcete provést místní upgrade jako součást řešení, otevření, zadat příznak <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_COPYBACKUP> jako `VSPUVF_FLAGS` parametr ve vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> implementace.

4. Pro oba kroky 2 a 3, skutečný soubor upgradovat kroky, pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>, je možné implementovat, jak je popsáno v "implementace `IVsProjectUpgade`" níže v části, nebo můžete delegovat skutečný soubor inovace <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>.

5. Použití metod pro posunutí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> účtovat inovace související zprávy pro uživatele pomocí Průvodce migrací sady Visual Studio.

6. <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileUpgrade> rozhraní se používá k implementaci jakýkoli druh upgradu souboru, který potřebuje provést jako součást upgradu projektu. Toto rozhraní není volána z <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>, ale je poskytnut jako mechanismus pro upgradování souborů, které jsou součástí systém projektu, ale systém hlavní projekt nemusí být přímo vědět. Například této situaci může dojít, pokud nejsou stejné vývojovým týmem, který zpracovává rest systém projektu zpracovává soubory a vlastnosti související s kompilátor.

### <a name="ivsprojectupgrade-implementation"></a>IVsProjectUpgrade Implementation

Pokud váš systém projektu implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> pouze, se nemůže účastnit **Průvodce převodu Visual Studio**. Nicméně i v případě, že implementujete <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> rozhraní, můžete stále delegovat upgrade souboru na <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> implementace.

#### <a name="to-implement-ivsprojectupgrade"></a>K implementaci IVsProjectUpgrade

1. Když se uživatel pokusí otevřít projekt, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> metoda je volána metodou prostředí po otevření projektu a před žádný jiný uživatel můžete provést akce na projektu. Pokud uživatel měl byl již výzva k upgradu řešení, pak bude <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> příznak je předáno `grfUpgradeFlags` parametru. Pokud uživatel otevře projekt přímo, takový tak, jak pomocí **přidat existující projekt** příkaz, pak bude <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> příznak nebude zadán, využije a projekt musí zobrazit výzvu uživateli pro upgrade.

2. V reakci <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> volání, projekt musí být vyhodnocen, zda soubor projektu se upgraduje. Pokud projekt není nutné upgradovat projekt na novou verzi, pak můžete jednoduše vrátit <xref:Microsoft.VisualStudio.VSConstants.S_OK> příznak.

3. Pokud projekt je potřeba upgradovat projekt na novou verzi, pak musíte určit, zda soubor projektu je možné upravovat prostřednictvím volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> metoda a předání hodnotou <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags> pro `rgfQueryEdit` parametru. Projekt se pak musí provést následující kroky:

    - Pokud `VSQueryEditResult` hodnotu vrácenou v `pfEditCanceled` parametr je <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditOK>, pak upgradu můžete pokračovat, protože soubor projektu lze zapsat.

    - Pokud `VSQueryEditResult` hodnotu vrácenou v `pfEditCanceled` parametr je <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> a `VSQueryEditResult` má hodnotu <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyNotUnderScc> bit sady, pak <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> musí, vrátí hodnotu neúspěch, protože uživatelé by se měly vyřešit oprávnění vydat sami. Projekt by potom postupujte takto:

         Ohlaste chybu uživatele voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> a vraťte se <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED> kód chyby <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>.

    - Pokud `VSQueryEditResult` hodnotu <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> a `VSQueryEditResultFlags` má hodnotu <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> bit sady, pak soubor projektu by měl být rezervován voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ForceEdit_NoPrompting>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_DisallowInMemoryEdits>,...).

4. Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> volání v souboru projektu způsobí, že soubor, který má být rezervován a nejnovější verzi, která se má načíst a potom projekt a projekt znovu načíst. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> Metoda je volána znovu, jakmile se vytvoří další instance projektu. V této druhé volání lze zapsat soubor projektu na disk. doporučuje se, že projekt uložení kopie souboru projektu ve starším formátu s. PŮVODNÍ rozšíření, proveďte jeho upgrade potřebné změny a uložte soubor projektu v novém formátu. Znovu, pokud libovolná součást procesu upgradu se nezdaří, metoda musíte uvést selhání tak, že vrací <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED>. To způsobí, že projekt tak, aby nenačte v Průzkumníkovi řešení.

     Je důležité pochopit, dokončení procesu, který se nachází v prostředí pro případ, ve kterém volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> – metoda (zadáte třeba hodnotu jen) vrátí <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> a <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> příznaky.

5. Uživatel se pokusí otevřít soubor projektu.

6. Prostředí volá vaši <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> implementace.

7. Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> vrátí `true`, pak volání prostředí vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> implementace.

8. Prostředí volá vaši <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> implementace otevřete soubor a inicializovat objekt projektu, například Project1.

9. Prostředí volá vaši `IVsProjectUpgrade::UpgradeProject` implementace k určení, zda soubor projektu je potřeba upgradovat.

10. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> a předejte hodnotu <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ReportOnly> pro `rgfQueryEdit` parametru.

11. Vrátí prostředí <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> pro `VSQueryEditResult` a <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> bit nastaven `VSQueryEditResultFlags`.

12. Vaše <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> volání implementace `IVsQueryEditQuerySave::QueryEditFiles` (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ForceEdit_NoPrompting>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_DisallowInMemoryEdits>).

Toto volání může způsobit, že novou kopii souboru projektu jej rezervovat a načíst nejnovější verzi, a také potřeba znovu načíst soubor projektu. V tomto okamžiku jeden ze dvou kroků situace:

- Pokud je zpracovat vlastní opakované načtení projektu, pak prostředí volá vaši <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> implementace (VSITEMID_ROOT). Když obdržíte toto volání, znovu načíst první instance vašeho projektu (Project1) a pokračovat v upgradu souboru projektu. Prostředí ví zpracování vlastní opakované načtení projektu, pokud se vrátíte `true` pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID.VSHPROPID_HandlesOwnReload>).

- Pokud nezpracovávají vlastní opakované načtení projektu, pak se vrátit `false` pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID.VSHPROPID_HandlesOwnReload>). V takovém případě před <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>(QEF_ForceEdit_NoPrompting, QEF_DisallowInMemoryEdits) vrátí prostředí vytvoří novou instanci jiného projektu, například "project2", následujícím způsobem:

    1. Prostředí volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.Close%2A> na váš první projekt objekt, Project1, tedy umístit tento objekt v neaktivním stavu.

    2. Prostředí volá vaši `IVsProjectFactory::CreateProject` implementace vytvořit druhou instanci projektu "project2".

    3. Prostředí volá vaši `IPersistFileFormat::Load` implementace otevřete soubor a inicializovat druhý objekt projektu "project2".

    4. Prostředí volá `IVsProjectUpgrade::UpgradeProject` podruhé k určení, zda objekt projektu by měl upgradovat. Ale tento přišla na nový, druhé instance projektu "project2". Jedná se o projekt, který je v řešení otevřen.

        > [!NOTE]
        > V instanci, která svůj první projekt Project1, se umístí do neaktivního stavu, pak musí vracet <xref:Microsoft.VisualStudio.VSConstants.S_OK> z prvního volání vaše <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> implementace.

    5. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> a předejte hodnotu <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ReportOnly> pro `rgfQueryEdit` parametru.

    6. Vrátí prostředí <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditOK> a upgradu můžete pokračovat, protože soubor projektu lze zapsat.

Pokud chcete upgradovat, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED> z `IVsProjectUpgrade::UpgradeProject`. Pokud žádný upgrade je nezbytné nebo jste vybrali možnost upgrade, zpracovávat `IVsProjectUpgrade::UpgradeProject` volat jako no-op. Pokud se vrátíte <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED>, zástupný uzel je přidán do řešení pro váš projekt.

## <a name="upgrading-project-items"></a>Upgrade položky projektu

Je-li přidat nebo spravovat položky uvnitř systémů projektů, které neimplementuje, budete muset účastnit v procesu upgradu projektu. Crystal Reports je příklad položky, kterou lze přidat do projektu systému.

Obvykle implementátory položky projektu chcete využít již plně vytvořenou instanci a upgradovat projekt, protože potřebují vědět, jaké jsou odkazy na projekt a jaké jiné vlastnosti projektu jsou existuje pro rozhodnutí upgradu.

### <a name="to-get-the-project-upgrade-notification"></a>Chcete-li získat oznámení o upgradu projektu

1. Nastavte <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80.SolutionOrProjectUpgrading> příznak (definováno v vsshell80.idl) ve vaší implementaci položky projektu. To způsobí, že položky projektu VSPackage zatížení automaticky při prostředí sady Visual Studio zjistí, že bude systém projektu probíhá upgrade.

2. Doporučte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> rozhraní prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution2.AdviseSolutionEvents%2A> metoda.

3. <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> Rozhraní je aktivována po dokončení upgradu operací implementace systému projektu a je vytvořen nový upgradovaný projekt. V závislosti na scénáři <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> rozhraní je aktivována po <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>, nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> metody.

### <a name="to-upgrade-the-project-item-files"></a>Upgradovat soubory položek projektu

1. Proces zálohování souboru musíte pečlivě spravovat ve vaší implementaci položky projektu. To platí zejména pro zálohování vedle sebe, kde `fUpgradeFlag` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> metoda je nastavena na <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP>, kde jsou umístěny soubory, které se má zálohovat společně na straně soubory, které jsou označeny jako "old". Zálohované soubory starší než systémový čas, kdy byl projekt upgradovat, lze označit jako zastaralé. Kromě toho se může přepsat, pokud nebyla provést určité kroky, pokud tomu chcete zabránit.

2. Položky projektu v době získá oznámení o upgrade projektu **Průvodce převodu Visual Studio** pořád zobrazuje. Proto měli používat metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> rozhraní kvůli upgradu zprávy do Průvodce vytvořením uživatelského rozhraní.

## <a name="see-also"></a>Viz také:

- [Projekty](../../extensibility/internals/projects.md)