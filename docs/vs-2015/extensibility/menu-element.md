---
title: Menu Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, Menus
- Menus element (VSCT XML schema)
ms.assetid: ce0560f3-b4c9-4ab2-a99c-d4e10f37b9e0
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 79a8fafc748274015dac7f8f0938bba37ba5a8bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194356"
---
# <a name="menu-element"></a>Menu – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definuje jednu položku nabídky. Toto jsou šest typů nabídek: Kontext, nabídky, MenuController, MenuControllerLatched, nástrojů a ToolWindowToolbar.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Menu guid=”guidMyCommandSet” id=”MyCommand” priority=”0x100” type=”button”>  
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
|guid|Povinný parametr. Identifikátor GUID identifikátoru GUID a ID příkazu.|  
|id|Povinný parametr. ID identifikátoru GUID a ID příkazu.|  
|priority|Volitelné. Číselná hodnota, která určuje relativní umístění nabídky ve skupině nabídek.|  
|ToolbarPriorityInBand|Volitelné. Číselná hodnota, která určuje relativní pozici panelu nástrojů ve svazku, když je toto okno ukotveno.|  
|– typ|Volitelné. Výčtová hodnota, která určuje typ prvku.<br /><br /> Pokud není k dispozici, je výchozí typ nabídky.<br /><br /> Kontext<br /> Místní nabídka, která se zobrazí, když uživatel klepne pravým tlačítkem myši časového období. Místní nabídka má následující vlastnosti:<br /><br /> -V nabídce se zobrazí jako místní nabídky nebude používat pole nadřazený a Priority.<br />– Je možné jako podnabídku a také jako místní nabídky. V tomto případě jsou dodržovány pole ID skupiny a Priority.<br />-Je vždy dostupná.<br /><br /> Místní nabídce se zobrazí jenom v případě, že jsou splněny následující podmínky:<br /><br /> –, Který je hostitelem ho se zobrazí okno.<br />-Obslužnou rutinu myši v sady VSPackage zjistí kliknutí pravým tlačítkem myši na okno a potom volá metodu, která zpracovává příkaz.<br />– Místní nabídce se zobrazí při volání <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager.ShowContextMenu%2A> – metoda (doporučený postup) nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A> metody.<br /><br /> Nabídka<br /> Poskytuje rozevírací nabídky. Rozevírací nabídka má následující vlastnosti:<br /><br /> -Respektuje nadřazené do její definice.<br />– Musí mít nadřazenou skupinu nebo commandplacement – do skupiny.<br />-Může být podnabídky do jakéhokoli jiného typu nabídky.<br />-Se automaticky zobrazí pokaždé, když se zobrazí její nadřazené nabídky.<br />-Nevyžaduje provádění jakékoli VSPackage kód, který se zobrazí.<br /><br /> MenuController<br /> Obsahuje tlačítko rozdělení rozevírací nabídky, která se obvykle používá v panelech nástrojů. Zobrazí se nabídka MenuController má následující vlastnosti:<br /><br /> – Musí být obsažen v jiné nabídky prostřednictvím nadřazené nebo commandplacement –.<br />-Respektuje nadřazené do její definice.<br />-Může mít jakýkoli druh nabídce jako jeho nadřazený objekt.<br />-Je automaticky k dispozici pokaždé, když se zobrazí její nadřazené nabídky.<br />-Nevyžaduje, aby programový podporu, aby v nabídce Zobrazit.<br /><br /> Příkaz v nabídce tlačítka rozdělení je zobrazený na tlačítku pro nabídky. Příkaz zobrazí má jednu z následujících vlastností:<br /><br /> -Je poslední příkaz, který byl použit, pokud příkaz je stále zobrazí a povoleno.<br />-Je první zobrazené příkaz.<br /><br /> MenuControllerLatched<br /> Poskytuje rozevírací nabídky tlačítka rozdělení, pro které je možné zadat příkaz jako výchozí výběr označením příkazu jako stisknutého.<br /><br /> Stisknutí příkaz je příkaz, který je označen v nabídce jako vybrané, obvykle zobrazením zaškrtávací políčko. Příkaz můžete označením stisknutého, pokud má OLECMDF_LATCHED příznak nastaven na něm v implementaci `QueryStatus` metodu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Zobrazí se nabídka MenuControllerLatched má následující vlastnosti:<br /><br /> – Musí být obsažen v jiné nabídky prostřednictvím nadřazené skupiny nebo commandplacement –.<br />-Respektuje nadřazené do její definice.<br />-Může mít jakýkoli druh nabídce jako jeho nadřazený objekt.<br />-Je k dispozici pokaždé, když se zobrazí její nadřazené nabídky.<br />-Nevyžaduje, aby programový podporu, aby v nabídce Zobrazit.<br /><br /> Příkaz v nabídce tlačítka rozdělení je zobrazený na tlačítku pro nabídky. Příkaz zobrazí má jednu z následujících vlastností:<br /><br /> -Je první zobrazené příkaz, který je stisknutého.<br />-Je první zobrazené příkaz.<br /><br /> Panel nástrojů<br /> Obsahuje panel nástrojů. Panel nástrojů má následující vlastnosti:<br /><br /> -Ignoruje nadřazené do její definice.<br />-Nelze nastavit podnabídky žádné skupiny, dokonce ani s použitím commandplacement –.<br />-Je vždy zobrazit kliknutím **panely nástrojů** na **zobrazení** nabídky.<br />-Lze zobrazit pomocí [visibilityitem –](../extensibility/visibilityitem-element.md).<br />-Nevyžaduje žádný kód, vytvořte ho. Příklad, jak vytvořit panel nástrojů, naleznete v tématu [přidání panelu nástrojů](../extensibility/adding-a-toolbar.md).<br /><br /> ToolWindowToolbar<br /> Obsahuje panel nástrojů, který je připojen k okno konkrétní nástroje, stejně, jako je panel nástrojů připojen do vývojového prostředí.<br /><br /> -Ignoruje nadřazené do její definice.<br />-Nelze nastavit podnabídky žádné skupiny, dokonce ani s použitím commandplacement –.<br />-Se zobrazí jenom v případě, že se zobrazí okno nástroje, který je hostitelem panelu nástrojů a panelu nástrojů sady VSPackage explicitně přidá na panel nástrojů. To se většinou děje při získání vlastností hostitele nástrojů vytvoří panel nástrojů (reprezentovaná <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost> rozhraní) z rámce okna nástrojů a potom voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost.AddToolbar%2A> metody.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené|Volitelné. Nadřazený prvek položky nabídky.|  
|CommandFlag|Povinný parametr. Zobrazit [Command Flag – Element](../extensibility/command-flag-element.md). Platné hodnoty CommandFlag nabídky jsou následující:<br /><br /> -   **AlwaysCreate**<br />-   **DefaultDocked**<br />-   **DefaultInvisible** -tento příznak nemá vliv na displeji panely nástrojů.<br />-   **DontCache**<br />-   **DynamicVisibility** -tento příznak nemá vliv na displeji panely nástrojů.<br />-   **IconAndText**<br />-   **NoCustomize**<br />-   **NotInTBList**<br />-   **NoToolbarClose**<br />-   **TextChanges**<br />-   **TextIsAnchorCommand**|  
|Řetězce|Povinný parametr. Zobrazit [řetězce Element](../extensibility/strings-element.md). Podřízené `ButtonText` element musí být definován.|  
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