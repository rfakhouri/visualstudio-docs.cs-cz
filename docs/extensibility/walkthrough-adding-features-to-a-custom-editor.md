---
title: "Návod: Přidání funkce do vlastního editoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - add features
ms.assetid: bfe083b6-3e35-4b9c-ad4f-b30b9ff412a5
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: df3621d87ae80c0eee105183edbc97a4e7ade62f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-adding-features-to-a-custom-editor"></a>Návod: Přidání funkce do vlastního editoru
Po vytvoření vlastního editoru do něj může přidat další funkce.  
  
### <a name="to-create-an-editor-for-a-vspackage"></a>Chcete-li vytvořit editor pro VSPackage  
  
1.  Vytvoření vlastního editoru pomocí šablony projektu balíček Visual Studio.  
  
     Další informace najdete v tématu [návod: vytvoření vlastního editoru](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
2.  Rozhodněte, zda chcete, aby vaše editor pro podporu zobrazení jedné nebo více zobrazení.  
  
     Editor, který podporuje **nové okno** příkazu, nebo má zobrazení formuláře a kódu zobrazit, vyžaduje samostatné dokument datové objekty a objekty zobrazení dokumentu. V editoru, který podporuje pouze jedno zobrazení Datový objekt dokumentu a objekt zobrazení dokumentu se dají implementovat na stejný objekt.  
  
     Příklad více zobrazení, naleznete v části [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md).  
  
3.  Implementovat objekt pro vytváření editor implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní.  
  
     Další informace najdete v tématu [objekty Factory editoru](../extensibility/editor-factories.md).  
  
4.  Rozhodněte, jestli chcete jako editor používat aktivace na místě nebo zjednodušené vložení ke správě okna dokumentu zobrazení objektu.  
  
     Zjednodušené vnoření okno editor hostuje zobrazení standardní dokumentů, zatímco okno editoru s aktivace na místě hostitelem ovládacího prvku ActiveX nebo jiný aktivní objekt jako jeho zobrazení dokumentu. Další informace najdete v tématu [zjednodušené vložení](../extensibility/simplified-embedding.md) a [aktivace na místě](../extensibility/in-place-activation.md).  
  
5.  Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní pro zpracování příkazů.  
  
6.  Zadejte trvalost dokumentu a reakci na externí soubor změny následujícím způsobem:  
  
    1.  Chcete-li zachovat soubor, implementujte <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> a <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> na svém editoru dokumentu datový objekt.  
  
    2.  Reagovat na změny externí soubor, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> na svém editoru dokumentu datový objekt.  
  
        > [!NOTE]
        >  Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx> k získání ukazatele na `IVsFileChangeEx`.  
  
7.  Koordinovat události úpravy dokumentu s zdrojového kódu. Provedete to následujícím způsobem:  
  
    1.  Získání ukazatele na `IVsQueryEditQuerySave2` voláním `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>.  
  
    2.  Když dojde k první upravit událost, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> metoda.  
  
         To vyzývá uživatele k rezervovat soubor, pokud není již rezervován. Ujistěte se, zpracování stavu "soubor není rezervována" čelit chyby  
  
    3.  Podobně před uložením souboru, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> metoda.  
  
         Tato metoda zobrazí výzvu k uložení souboru, pokud ještě nebyl uložen nebo pokud se změnil od posledního uložení.  
  
8.  Povolit **vlastnosti** okna zobrazte vlastnosti vybraného textu v editoru. Provedete to následujícím způsobem:  
  
    1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> každý výběr textu čas změny předávání ve vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
    2.  Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> služby k získání ukazatele na <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
9. Povolit uživatelům přetažení položky mezi editoru a **sada nástrojů**, nebo mezi externí editory (například Microsoft Word) a **sada nástrojů**. Provedete to následujícím způsobem:  
  
    1.  Implementace `IDropTarget` na svém editoru rozhraní IDE upozorní, že je vaše editor cíle přetažení.  
  
    2.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> rozhraní v zobrazení, můžete povolit nebo zakázat položky ve svém editoru **sada nástrojů**.  
  
    3.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults%2A> a volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> služby k získání ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> rozhraní.  
  
         To umožňuje vaší VSPackage k přidání nových položek do **sada nástrojů**.  
  
10. Rozhodnete, zda má další volitelné funkce pro vaše editor.  
  
    -   Pokud chcete, aby vaše editor pro podporu najít a nahradit příkazy, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>.  
  
    -   Pokud chcete použít nástroj okno Osnova dokumentu ve svém editoru, implementujte `IVsDocOutlineProvider`.  
  
    -   Pokud chcete použít stavového řádku v editoru, implementujte <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> a volání `QueryService` pro <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> k získání ukazatele na `IVsStatusBar`.  
  
         Editor můžete například zobrazit řádku nebo informace o sloupci, režim výběru (stream / pole) a režim vložení (vložení / overstrike).  
  
    -   Pokud chcete, aby vaše editor pro podporu `Undo` příkaz, doporučuje se použití modelu manager OLE vrácení zpět. Jako alternativu, může mít popisovač editor `Undo` příkaz přímo.  
  
11. Vytvořte registru informace, včetně identifikátory GUID VSPackage, v nabídkách, editoru a dalších funkcí.  
  
     Následuje obecné příklad kódu, vložíte ve vašem souboru skriptu .rgs abychom ukázali, jak správně zaregistrovat editoru.  
  
    ```  
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
  
12. Implementujte Kontextová nápověda a odborná pomoc.  
  
     To umožňuje poskytovat podporu pro položky ve svém editoru Nápověda F1 a okno dynamické nápovědy. Další informace najdete v tématu [postup: Zadejte kontext pro editory](../extensibility/how-to-provide-context-for-editors.md).  
  
13. Vystaví objektový Model automatizace z vaší editor implementací `IDispatch` rozhraní.  
  
     Další informace najdete v tématu [přispívání do modelu automatizace](../extensibility/internals/contributing-to-the-automation-model.md).  
  
## <a name="robust-programming"></a>Robustní programování  
  
-   Instance editoru se vytvoří při volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda. Pokud editor podporuje více zobrazení `CreateEditorInstance` vytvoří data dokumentu i objekty zobrazení dokumentu. Pokud již dokument datový objekt otevřít, hodnotu null `punkDocDataExisting` předána hodnota `IVsEditorFactory::CreateEditorInstance`. Vaše implementace objektu factory editoru musí určit, zda je existující objekt dat dokumentu kompatibilní pomocí dotazů na příslušné rozhraní na něm. Další informace najdete v tématu [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md).  
  
-   Pokud chcete použít zjednodušenou vnoření přístup, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní.  
  
-   Pokud se rozhodnete použít aktivace na místě, implementujte následující rozhraní:  
  
     <xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>  
  
     <xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>  
  
    > [!NOTE]
    >  `IOleInPlaceComponent` Rozhraní se používá pro zabránění slučování nabídek OLE 2.  
  
     Vaše `IOleCommandTarget` implementace zpracovává příkazy, jako **Vyjmout**, **kopie**, a **vložení**. Při implementaci `IOleCommandTarget`, rozhodnout, jestli vaše editor vyžaduje, aby svůj vlastní soubor .vsct definovat vlastní struktury příkaz nabídky, nebo pokud ji můžete implementovat standardní příkazy, které jsou definované v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Obvykle editory používat a rozšířit nabídky prostředí IDE a definovat vlastní panely nástrojů. Ale často je nezbytné pro editor k definování vlastní určité příkazy kromě pomocí rozhraní IDE sady standardních příkazů. To pokud chcete udělat, je třeba deklarovat jako editor standardní příkazy pomocí a potom v souboru .vsct definujte všechny nové příkazy, kontextové nabídky, nejvyšší úrovně nabídek a panelů nástrojů. Pokud vytvoříte místní aktivace editor, pak implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> a definovat nabídek a panelů nástrojů pro editor v souboru .vsct místo použití slučování nabídek OLE 2.  
  
-   Pokud chcete zabránit příkazu nabídky nakupení v uživatelském rozhraní, používejte existující příkazy v prostředí IDE před inventing nové příkazy. Sdílené příkazy jsou definovány v SharedCmdDef.vsct a ShellCmdDef.vsct. Tyto soubory jsou nainstalovány ve výchozím nastavení v podadresáři VisualStudioIntegration\Common\Inc vaše [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] instalace.  
  
-   `ISelectionContainer`Výběr jednoho a víc můžete express. Každý vybraný objekt je implementovaný jako `IDispatch` objektu.  
  
-   Implementuje rozhraní IDE `IOleUndoManager` jako přístupný ze služby <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> nebo jako objekt, který se dá vytvořit instance prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A>. Vaše editor implementuje `IOleUndoUnit` rozhraní pro každou `Undo` akce.  
  
-   Existují dvě místa vlastní editor můžou zpřístupnit objekty automatizace:  
  
    -   `Document.Object`  
  
    -   `Window.Object`  
  
## <a name="see-also"></a>Viz také  
 [Přispívání do modelu automatizace](../extensibility/internals/contributing-to-the-automation-model.md)   
 [Postupy: Zadejte kontext pro editory](../extensibility/how-to-provide-context-for-editors.md)