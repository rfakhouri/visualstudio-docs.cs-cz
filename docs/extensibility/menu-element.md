---
title: Menu Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Menus
- Menus element (VSCT XML schema)
ms.assetid: ce0560f3-b4c9-4ab2-a99c-d4e10f37b9e0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5c44ca8a78a331d66d099b8d141c4b66c1144949
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="menu-element"></a>Menu Element
Definuje jednu položku nabídky. Toto jsou šesti druhy nabídky: kontextu, nabídky, MenuController, MenuControllerLatched, nástrojů a ToolWindowToolbar.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Menu guid="guidMyCommandSet" id="MyCommand" priority="0x100" type="button">  
  <Parent>... </Parent>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Menu>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.|  
|id|Požadováno. ID identifikátor GUID nebo ID příkazu.|  
|Priorita|Volitelné. Číselnou hodnotu, která určuje relativní umístění nabídky ve skupině nabídky.|  
|ToolbarPriorityInBand|Volitelné. Číselnou hodnotu, která určuje relativní pozici panelu nástrojů v pásmo, když je ukotvena okna.|  
|– typ|Volitelné. Výčtová hodnota, který určuje typ elementu.<br /><br /> Pokud není přítomný, je výchozí typ nabídky.<br /><br /> Kontext<br /> Místní nabídky, které se zobrazí, když uživatel klikne pravým tlačítkem myši časového období. Místní nabídky má následující vlastnosti:<br /><br /> -Nepoužívá pole nadřazené a Priority při nabídce se zobrazí jako místní nabídky.<br />-Lze použít jako podnabídky a také jako místní nabídky. V takovém případě jsou dodržovány pole ID skupiny a Priority.<br />-Je vždy není k dispozici.<br /><br /> Místní nabídky se zobrazí jenom v případě, že jsou splněné následující podmínky:<br /><br /> -Hostitelského okna se zobrazí.<br />– Obslužná rutina myši v VSPackage zjistí klikněte pravým tlačítkem na okna a potom volá metodu, která zpracovává příkaz.<br />– Místní nabídce se zobrazí při volání <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager.ShowContextMenu%2A> – metoda (jedná se o doporučený postup) nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A> metoda.<br /><br /> Nabídka<br /> Poskytuje rozevírací nabídce. Rozevírací nabídky má následující vlastnosti:<br /><br /> -Respektuje nadřízený prvek v jeho definice.<br />-Musí mít nadřazenou skupinu nebo CommandPlacement do skupiny.<br />-Může být podnabídky v jakékoli jiné nabídky.<br />-Se automaticky zobrazí vždy, když se zobrazí jeho nadřazený nabídky.<br />-Nevyžaduje implementace jakýkoli VSPackage kód, chcete-li zobrazit.<br /><br /> MenuController<br /> Poskytuje rozevírací nabídce tlačítko rozdělení, které se obvykle používá v panelech nástrojů. Z nabídky MenuController má následující vlastnosti:<br /><br /> – Musí být obsažena v jiné nabídky prostřednictvím nadřazené nebo CommandPlacement.<br />-Respektuje nadřízený prvek v jeho definice.<br />-Může mít jakýkoli druh nabídky jako svůj nadřazený uzel.<br />-Je automaticky k dispozici vždy, když se zobrazí jeho nadřazený nabídky.<br />-Nevyžaduje programové podpory, aby se v nabídce Zobrazit.<br /><br /> Příkaz z nabídky tlačítko rozdělení se zobrazí na tlačítka nabídky. Příkaz zobrazí má jeden z následujících vlastností:<br /><br /> -Je poslední příkaz, který byl použit, pokud příkaz je pořád zobrazí a povolený.<br />-Je první příkaz zobrazit.<br /><br /> MenuControllerLatched<br /> Poskytuje tlačítko rozdělení rozevírací nabídku pro kterou můžete třeba zadat příkaz jako výchozí výběr označením příkaz jako zajištěné.<br /><br /> Stisknutí příkaz je příkaz, který je označen v nabídce jako vybrané, obvykle zobrazením zaškrtnutí. Příkaz může být označen jako zajištěné, pokud má OLECMDF_LATCHED nastaven na něm v implementaci příznak `QueryStatus` metodu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Z nabídky MenuControllerLatched má následující vlastnosti:<br /><br /> – Musí být obsažena v jiné nabídky prostřednictvím nadřazené skupiny nebo CommandPlacement.<br />-Respektuje nadřízený prvek v jeho definice.<br />-Může mít jakýkoli druh nabídky jako svůj nadřazený uzel.<br />-Je k dispozici vždy, když se zobrazí jeho nadřazený nabídky.<br />-Nevyžaduje programové podpory, aby se v nabídce Zobrazit.<br /><br /> Příkaz z nabídky tlačítko rozdělení se zobrazí na tlačítka nabídky. Příkaz zobrazí má jeden z následujících vlastností:<br /><br /> -Je první zobrazené příkaz, který je zajištěné.<br />-Je první příkaz zobrazit.<br /><br /> Panel nástrojů<br /> Poskytuje panelu nástrojů. Panel nástrojů má následující vlastnosti:<br /><br /> -Ignoruje nadřízený prvek v jeho definice.<br />-Nelze vytvořit podnabídky jakékoli skupiny ani pomocí CommandPlacement.<br />-Lze vždy zobrazit kliknutím na **panely nástrojů** na **zobrazení** nabídky.<br />-Lze zobrazit pomocí [VisibilityItem](../extensibility/visibilityitem-element.md).<br />-Nevyžaduje žádný kód k jeho vytvoření. Příklad o tom, jak vytvořit panel nástrojů, naleznete v části [přidávání panelů nástrojů](../extensibility/adding-a-toolbar.md).<br /><br /> ToolWindowToolbar<br /> Poskytuje nástrojů, který je připojen k okno konkrétní nástroje, stejně jako panelu nástrojů je připojen k vývojového prostředí.<br /><br /> -Ignoruje nadřízený prvek v jeho definice.<br />-Nelze vytvořit podnabídky jakékoli skupiny ani pomocí CommandPlacement.<br />-Se zobrazí jenom v případě, že se zobrazí panel nástrojů, který je hostitelem panelu nástrojů a panelu nástrojů VSPackage explicitně přidá do okno nástroje. To se obvykle provádí při vytvoří získání vlastnost hostitele panel nástrojů panel nástrojů (reprezentovaná <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost> rozhraní) z nástroje rámec okna a potom volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost.AddToolbar%2A> metoda.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené|Volitelné. Položky nabídky nadřazeného elementu.|  
|CommandFlag|Požadováno. V tématu [příkaz příznak Element](../extensibility/command-flag-element.md). Platné hodnoty CommandFlag nabídky jsou následující:<br /><br /> -   **AlwaysCreate**<br />-   **DefaultDocked**<br />-   **DefaultInvisible** -tento příznak nemá vliv na zobrazení panely nástrojů.<br />-   **DontCache**<br />-   **DynamicVisibility** -tento příznak nemá vliv na zobrazení panely nástrojů.<br />-   **IconAndText**<br />-   **NoCustomize**<br />-   **NotInTBList**<br />-   **NoToolbarClose**<br />-   **TextChanges**<br />-   **TextIsAnchorCommand**|  
|Řetězce|Požadováno. V tématu [řetězce Element](../extensibility/strings-element.md). Podřízená `ButtonText` element musí být definován.|  
|Poznámka|Volitelný komentář.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Menus – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
  
## <a name="example"></a>Příklad  
  
```  
<Menu guid="cmdGuidWidgetCommands" id="menuIDEditWidget"  
  priority="0x0002" type="Menu">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
    <CommandFlag>AlwaysCreate</CommandFlag>  
    <Strings>  
      <ButtonText>Edit Widget</ButtonText>  
    </Strings>  
    </Parent>  
</Menu>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)