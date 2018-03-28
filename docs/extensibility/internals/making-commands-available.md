---
title: Zpřístupnění příkazy | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- best practices, menu and toolbar commands
- toolbars [Visual Studio], best practices
- menu commands, best practices
ms.assetid: 3ffc4312-c6db-4759-a946-a4bb85f4a17a
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 88f29f575cc59b365978376f01f53f2624c31cd0
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="making-commands-available"></a>Zpřístupnění příkazy
Po přidání více VSPackages k sadě Visual Studio, může se pomocí příkazů přeplněné uživatelské rozhraní (UI). Můžete naprogramovat vašeho balíčku, abyste tento problém omezili, následujícím způsobem:

-   Program balíčku tak, aby je načtena, jenom když se uživatel vyžaduje.

-   Program balíčku tak, aby jeho příkazy se zobrazí jenom v případě, že mohou být vyžadovány v kontextu aktuálního stavu integrované vývojové prostředí (IDE).

## <a name="delayed-loading"></a>Odložené načtení
 Odložené načtení je typické způsob, jak povolit navrhnout VSPackage tak, aby jeho příkazy se zobrazí v uživatelském rozhraní, ale balíček samotné není načíst, dokud uživatel klikne příkazy. K tomu, v souboru .vsct vytvořte příkazy, které mají žádné příznaky příkazu.

 Následující příklad ukazuje definici příkazu nabídky ze souboru .vsct. Toto je příkaz, který je generován šablonu pro balíček Visual Studio při **příkaz nabídky** je vybraná možnost v šabloně.

```xml
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />
  <Icon guid="guidImages" id="bmpPic1" />
  <Strings>
    <CommandName>cmdidTestCommand</CommandName>
    <ButtonText>Test Command</ButtonText>
  </Strings>
</Button>

```

 V příkladu Pokud nadřazené skupiny, `MyMenuGroup`, je podřízená nabídek nejvyšší úrovně, jako **nástroje** nabídky, příkaz se nebude zobrazovat v této nabídce, ale balíček, který spouští příkaz nebudou načteny, dokud se po kliknutí na příkaz uživatelem. Nicméně ve programování příkaz k implementaci <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, můžete povolit balíček, který chcete načíst, pokud je v nabídce, která obsahuje příkaz nejprve rozbalen.

 Všimněte si, že zpožděné načítání může také zvýšit výkon spuštění.

## <a name="current-context-and-the-visibility-of-commands"></a>Aktuální kontext a viditelnost příkazy
 Můžete naprogramovat VSPackage příkazy jako viditelný nebo skrytý, v závislosti na aktuální stav VSPackage dat nebo akce, které jsou aktuálně relevantní. Můžete povolit VSPackage pro nastavení stavu příkazů, obvykle pomocí implementace <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> metoda z <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, ale to vyžaduje VSPackage má být načten předtím, než se může spustit kód. Místo toho doporučujeme povolit IDE ke správě viditelnosti příkazy bez načtení balíčku. Uděláte to, že v souboru .vsct přidružit příkazy nejméně jeden speciální kontext uživatelského rozhraní. Tyto kontexty uživatelského rozhraní jsou identifikovány identifikátor GUID říká *příkaz kontextu GUID*.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] monitoruje změny, které jsou výsledkem uživatele akcí, například načítání projektu nebo z úpravy chystáte sestavení. Změny jsou prováděny, je automaticky změnit vzhled rozhraní IDE. Následující tabulka uvádí čtyři hlavní kontextech IDE změnit, který [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] monitorování.

|Typ kontextu|Popis|
|---------------------|-----------------|
|Typ aktivního projektu|U většiny typů projektu to `GUID` hodnota je stejný jako identifikátor GUID VSPackage, který implementuje projektu. Ale [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projekty použít typ projektu `GUID` jako hodnotu.|
|Aktivní okno|Obvykle je to poslední okno aktivní dokument, který stanoví aktuální kontext uživatelského rozhraní pro vazeb klíče. Však mohou být také okno nástroje, který má vazbu na klíč tabulku, která se podobá interní webového prohlížeče. Pro více kartami dokumentu windows, jako je například HTML editor, má každé kartě kontextu jiný příkaz `GUID`.|
|Služba Active jazyka|Služba jazyka, který je přidružený soubor, který je aktuálně zobrazený v textovém editoru.|
|Okno Active nástroje|Okno nástroje, které je otevřený a má právě fokus.|

 Páté oblast hlavní kontextu je stav uživatelského rozhraní IDE. Kontexty uživatelského rozhraní se identifikují podle kontextu aktivní příkaz `GUID`s následujícím způsobem:

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionBuilding_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Debugging_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Dragging_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.FullScreenMode_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.DesignMode_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.NoSolution_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.EmptySolution_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionHasSingleProject_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionHasMultipleProjects_guid>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.CodeWindow_guid>

 Tyto identifikátory GUID jsou označeny jako aktivní nebo neaktivní, v závislosti na aktuální stav rozhraní IDE. Ve stejnou dobu může být aktivní více kontexty uživatelského rozhraní.

### <a name="hiding-and-displaying-commands-based-on-context"></a>Skrytí a zobrazením příkazů na základě kontextu
 Můžete zobrazit nebo skrýt příkaz balíčku v prostředí IDE bez načítání balíčku sám sebe. K tomu, zadejte příkaz v souboru .vsct balíčku pomocí `DefaultDisabled`, `DefaultInvisible`, a `DynamicVisibility` příkaz příznaky a přidat jednu nebo více [VisibilityItem](../../extensibility/visibilityitem-element.md) elementů [ VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) části. Pokud zadaný příkaz kontextu `GUID` stane aktivní, se zobrazí příkaz bez načtení balíčku.

### <a name="custom-context-guids"></a>Vlastní kontextu identifikátory GUID
 Pokud příslušný příkaz kontextu, identifikátor GUID není již definována, můžete definovat jeden ve vašem VSPackage a pak programu mohla být aktivní nebo neaktivní podle potřeby řízení zobrazení vaší příkazů. Použití <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> službu:

-   Zaregistrovat kontextu identifikátory GUID (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> metoda).

-   Zjištění stavu kontextu `GUID` (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metoda).

-   Zapnout kontextu `GUID`s zapnout a vypnout (voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> metoda).

    > [!CAUTION]
    > Zajistěte, aby vaše VSPackage vzhledem k tomu může jsou na nich závislé jiné VSPackages neovlivní stav všechny existující kontext identifikátor GUID.

## <a name="example"></a>Příklad
 Následující příklad příkazu VSPackage ukazuje dynamické viditelnost příkaz, který spravuje příkaz kontexty bez načítání VSPackage.

 Příkaz je nastavena na povolena a vždy, když existuje řešení; To znamená vždy, když je jeden z následujících kontextu příkaz identifikátory GUID aktivní:

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>

-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>

V příkladu, Všimněte si, že každý příkaz příznak je samostatné [příkaz příznak](../../extensibility/command-flag-element.md) elementu.

```xml
<Button guid="guidDynamicVisibilityCmdSet" id="cmdidMyCommand"
        priority="0x0100" type="Button">
  <Parent guid="guidDynamicVisibilityCmdSet" id="MyMenuGroup" />
  <Icon guid="guidImages" id="bmpPic1" />
  <CommandFlag>DefaultDisabled</CommandFlag>
  <CommandFlag>DefaultInvisible</CommandFlag>
  <CommandFlag>DynamicVisibility</CommandFlag>
  <Strings>
    <CommandName>cmdidMyCommand</CommandName>
    <ButtonText>My Command name</ButtonText>
  </Strings>
</Button>
```

Také Všimněte si, že každý kontext uživatelského rozhraní musí být v samostatné uveden `VisibilityItem` element následujícím způsobem.

```xml
<VisibilityConstraints>
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                  id="cmdidMyCommand" context="UICONTEXT_EmptySolution" />
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                      id="cmdidMyCommand" context="UICONTEXT_SolutionHasSingleProject" />
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"
                  id="cmdidMyCommand" context="UICONTEXT_SolutionHasMultipleProjects" />
</VisibilityConstraints>
```

## <a name="see-also"></a>Viz také

- [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)
- [Dynamické přidávání položek nabídky](../../extensibility/dynamically-adding-menu-items.md)