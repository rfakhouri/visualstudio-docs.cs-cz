---
title: 'Návod: Přidávání funkcí do vlastního editoru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - add features
ms.assetid: bfe083b6-3e35-4b9c-ad4f-b30b9ff412a5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 50565363f2fc88e40816bdfc4773e436e960ee06
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66312887"
---
# <a name="walkthrough-add-features-to-a-custom-editor"></a>Návod: Přidání funkcí do vlastního editoru
Po vytvoření vlastního editoru můžete k němu přidat další funkce.

## <a name="to-create-an-editor-for-a-vspackage"></a>Chcete-li vytvořit editor pro balíček VSPackage

1. Vytvoření vlastního editoru pomocí šablony projektu balíček Visual Studio.

     Další informace najdete v tématu [názorný postup: Vytvoření vlastního editoru](../extensibility/walkthrough-creating-a-custom-editor.md).

2. Rozhodněte, jestli chcete editor pro podporu zobrazení jedné nebo více zobrazení.

     Editor, který podporuje **nové okno** příkazu, nebo obsahuje zobrazení formuláře a zobrazení kódu, vyžaduje samostatnou dokumentu datové objekty a objekty zobrazení dokumentu. V editoru, který podporuje pouze jedno zobrazení je možné implementovat datový objekt dokumentu a objekt zobrazení dokumentu na stejný objekt.

     Příklad více zobrazení, naleznete v tématu [podporovat více zobrazení dokumentů](../extensibility/supporting-multiple-document-views.md).

3. Implementovat objekt pro vytváření editoru nastavením <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní.

     Další informace najdete v tématu [objekty pro vytváření editoru](../extensibility/editor-factories.md).

4. Rozhodněte, jestli chcete editor k použití aktivace na místě nebo zjednodušená vkládání pro správu okna dokumentu zobrazení objektu.

     Zjednodušená vkládání okno editoru hostitelem zobrazení dokumentu standardu během místní aktivace okno editoru hostuje ovládací prvek ActiveX nebo jiný aktivní objekt jako jeho zobrazení dokumentu. Další informace najdete v tématu [zjednodušená vkládání](../extensibility/simplified-embedding.md) a [aktivace na místě](../extensibility/in-place-activation.md).

5. Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní pro zpracování příkazů.

6. Zadejte trvalost dokumentu a reakci na externí soubor změny:

    1. Chcete-li zachovat soubor, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> a <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> na váš editor dokumentu datový objekt.

    2. Chcete-li reagovat na změny externí soubor, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> na váš editor dokumentu datový objekt.

        > [!NOTE]
        > Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx> získat ukazatel na `IVsFileChangeEx`.

7. Koordinovat událostí úpravy dokumentu pomocí správy zdrojového kódu. Postupujte podle těchto kroků:

    1. Získat ukazatel na `IVsQueryEditQuerySave2` voláním `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>.

    2. Volání při výskytu první události edit <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> metody.

         Tato metoda se zobrazí výzva k rezervovat soubor, pokud ještě není rezervován. Ujistěte se, že zpracování "soubor není rezervován" stavu, aby se předešlo chybám.

    3. Obdobně volat před uložením tohoto souboru, <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> metody.

         Tato metoda se zobrazí výzva k uložení souboru, pokud nebyla uložena, nebo pokud se změnily od posledního uložení.

8. Povolit **vlastnosti** okno k zobrazení vlastností vybraného textu v editoru. Postupujte podle těchto kroků:

    1. Volání <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> výběr textu každý čas změny předáním hodnoty ve vaší implementaci <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.

    2. Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> služby k získání ukazatele na <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.

9. Povolit uživatelům přetahování položek mezi editoru a **nástrojů**, nebo mezi externích editorech (například Microsoft Word) a **nástrojů**. Postupujte podle těchto kroků:

    1. Implementace `IDropTarget` na editor k upozornění rozhraní IDE, editor je cíl přetažení.

    2. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> rozhraní pro zobrazení, můžete povolit nebo zakázat položky v editoru **nástrojů**.

    3. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults%2A> a volat `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> služby k získání ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> rozhraní.

         Tyto kroky aktivují vašeho balíčku VSPackage pro přidání nové položky **nástrojů**.

10. Rozhodněte, zda chcete další volitelné funkce pro editor.

    - Pokud chcete, aby váš editor pro podporu najít a nahradit příkazy, implementujte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>.

    - Pokud chcete použít okno nástroje osnovy dokumentu v editoru, implementovat `IVsDocOutlineProvider`.

    - Pokud chcete použít stavového řádku v editoru, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> a volat `QueryService` pro <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> získat ukazatel na `IVsStatusBar`.

         Editor může například zobrazit řádku / informace o sloupci, režim výběru (datový proud stream / pole) a režim vložení (vložení / overstrike).

    - Pokud chcete, aby váš editor pro podporu `Undo` příkazu, doporučujeme použít model Správce akcí zpět OLE. Jako alternativu můžete použít editor popisovač `Undo` přímo příkazu.

11. Vytvoření registru informace, včetně identifikátory GUID pro sady VSPackage, nabídky, editor a další funkce.

     Obecný příklad kódu, který vložíte do vaší *.rgs* soubor skriptu ukazují, jak správně zaregistrovat editoru.

    ```csharp
    NoRemove Editors
    {
          ForceRemove {...guidEditor...} = s 'RTF Editor'
          {
             val Package = s '{...guidVsPackage...}'
             ForceRemove Extensions
             {
                val rtf = d 50
             }
          }
    }
    NoRemove Menus
    {
          val {...guidVsPackage...} = s ',203,11'
    }
    ```

12. Implementace podpora kontextové nápovědy.

     Tento krok umožňuje poskytovat podporu pro položky v editoru Nápověda F1 a okna dynamické nápovědy. Další informace najdete v tématu [jak: Poskytuje kontext pro editory](../extensibility/how-to-provide-context-for-editors.md).

13. Vystavení modelu automatizačních objektů z editoru implementací `IDispatch` rozhraní.

     Další informace najdete v tématu [přispívání do modelu automatizace](../extensibility/internals/contributing-to-the-automation-model.md).

## <a name="robust-programming"></a>Robustní programování

- Je vytvořena instance editoru, když volá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody. Pokud editor podporuje několik zobrazení `CreateEditorInstance` vytvoří data dokumentu a zobrazit objekty dokumentu. Pokud už je datový objekt dokumentu otevřít, nenulovým `punkDocDataExisting` je předána hodnota `IVsEditorFactory::CreateEditorInstance`. Vaše implementace objektu factory editoru musí zjistit, zda je existující objekt data dokumentu kompatibilní pomocí dotazu pro příslušné rozhraní. Další informace najdete v tématu [podpora více zobrazení dokumentů](../extensibility/supporting-multiple-document-views.md).

- Pokud používáte zjednodušený postup pro vkládání, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní.

- Pokud se rozhodnete použít aktivace na místě, implementace následujících rozhraní:

   <xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>

   <xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>

   <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>

  > [!NOTE]
  > `IOleInPlaceComponent` Rozhraní se používá pro zabránění OLE 2 slučování nabídek.

   Vaše `IOleCommandTarget` implementace zpracovává příkazy, jako **Vyjmout**, **kopírování**, a **vložit**. Při implementaci `IOleCommandTarget`, rozhodněte, jestli váš editor vyžaduje vlastní *.vsct* souboru definovat vlastní struktury příkaz nabídky nebo pokud jej můžete implementovat standardní příkazy určené [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Obvykle editory použít a rozšířit rozhraní IDE nabídky a definovat jejich vlastní panely nástrojů. Často je však nutné definovat vlastní specifické příkazy kromě pomocí rozhraní IDE sady standardních příkazů editoru. Musí deklarovat používá standardní příkazy a potom definovat, nových příkazů, kontextové nabídky, nejvyšší úrovně nabídky a panely nástrojů v editoru *.vsct* souboru. Je-li vytvořit místní aktivace editoru implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> a definovat nabídek a panelů nástrojů editoru v *.vsct* souboru namísto použití OLE 2 slučování nabídek.

- Aby se zabránilo nakupení v uživatelském rozhraní příkaz nabídky, používejte stávajících příkazů v integrovaném vývojovém prostředí před inventing nových příkazů. Sdílené příkazy jsou definovány v *SharedCmdDef.vsct* a *ShellCmdDef.vsct*. Tyto soubory jsou nainstalovány ve výchozím nastavení v podadresáři VisualStudioIntegration\Common\Inc vaše [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] instalace.

- `ISelectionContainer` můžete vyjádřit jednu i více výběrů. Každý vybraný objekt je implementovaný jako `IDispatch` objektu.

- Implementuje rozhraní IDE `IOleUndoManager` jako služby přístupné <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> nebo jako objekt, který se dá vytvořit instance prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A>. Váš editor implementuje `IOleUndoUnit` rozhraní pro každou `Undo` akce.

- Existují dvě místa vlastního editoru můžete zveřejnit objekty automatizace:

  - `Document.Object`

  - `Window.Object`

## <a name="see-also"></a>Viz také:
- [Přispívání do modelu automatizace](../extensibility/internals/contributing-to-the-automation-model.md)
- [Postupy: Poskytuje kontext pro editory](../extensibility/how-to-provide-context-for-editors.md)