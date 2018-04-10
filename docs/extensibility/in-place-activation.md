---
title: Aktivace na místě | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - in-place view activation
ms.assetid: 7d316945-06e0-4d8e-ba3a-0ef96fc75399
caps.latest.revision: 26
manager: douge
ms.openlocfilehash: d1fe2c1dfe71923897836f803e3a9712b4dec0f1
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="in-place-activation"></a>Aktivace na místě
Pokud editor zobrazení hostitelem ActiveX nebo jiných active ovládacích prvků, je nutné implementovat editor zobrazení jako ovládací prvek ActiveX, nebo jako objekt dat aktivní dokument, který používá model aktivace na místě.  
  
## <a name="support-for-menus-toolbars-and-commands"></a>Podpora pro nabídky, panely nástrojů a příkazy  
 Visual Studio umožňuje zobrazení editor používat nabídek a panelů nástrojů rozhraní IDE. Tato rozšíření jsou označovány jako *OLE místní součásti*. Další informace najdete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> a <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager>.  
  
 Pokud budete implementovat ovládací prvek ActiveX, je možné hostovat další vložené objekty. Pokud budete implementovat objekt dat dokumentu, omezí rámce okna možnost používat ovládací prvky ActiveX.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocumentView> rozhraní povolit pro oddělení dat a zobrazení. Ale Visual Studio nepodporuje tuto funkci, a tato rozhraní slouží pouze k reprezentaci objekt zobrazení dokumentu.  
  
 Editory, které používají <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> služby můžete zadat nabídky panelu nástrojů a integrace příkaz voláním metody <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> rozhraní implementované <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> služby. Editory můžete také nabízí jiné funkce sady Visual Studio, jako je výběr pro sledování a správu vrátit zpět. Další informace najdete v tématu [vytváření vlastní editory a návrhářů,](../extensibility/creating-custom-editors-and-designers.md).  
  
## <a name="objects-and-interfaces-used"></a>Objekty a používá rozhraní  
 Na následujícím obrázku jsou zobrazeny objekty, které se používají k vytvoření aktivace na místě.  
  
 ![V&#45;umístit aktivace Editor](../extensibility/media/vsinplaceactivationeditor.gif "vsInPlaceActivationEditor")  
Editor aktivace na místě  
  
> [!NOTE]
>  Objekty v této kreslení, jenom `CYourEditorFactory` objektu je potřeba vytvořit standardní editor. Pokud vytváříte vlastní editor, není nutné k implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> vzhledem k tomu, že vaše editor pravděpodobně bude mít svůj vlastní mechanismus privátní trvalosti. Další informace najdete v tématu [vytváření vlastní editory a návrhářů,](../extensibility/creating-custom-editors-and-designers.md).  
  
 Všechna rozhraní, které jsou implementovány vytvořit místní aktivace editor jsou zobrazeny na jedné `CYourEditorDocument` objektu, ale tato konfigurace podporuje pouze jediné zobrazení data dokumentu. Další informace o podpoře více zobrazení dat dokumentu najdete v tématu [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md).  
  
|Rozhraní|Typ objektu|Použití|  
|---------------|--------------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>|Zobrazit|Umožňuje místní objekty VSPackage pracovat jako plně integrované komponenty rozhraní IDE pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> služby. Tato služba integruje nabídek, panely nástrojů a příkazy objektu do rozhraní IDE a oznámení změny stavu.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>|Zobrazit|Hlavní znamená, podle kterého vložený objekt poskytuje základní funkce k jejímu kontejneru a komunikuje s ním.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>|Zobrazit|Spravuje aktivace a deaktivace objektů na místě a určuje, kolik objektu na místě by měly jít vidět.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceObject>|Zobrazit|Poskytuje přímý kanál komunikace mezi objekt na místě, oken s rámečkem nejkrajnější přidružené aplikace a okna v aplikaci, která obsahuje vložený objekt.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>|Zobrazit|Implementuje objekt ActiveX. Všimněte si, že metody <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocumentView> že dat samostatné dokumentů a zobrazení není použit v prostředí IDE.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Zobrazení nebo Data|Umožňuje dokumentu datový objekt nebo objekt zobrazení dokumentu nebo i k účasti ve zpracování příkazu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|Zobrazit|Umožňuje aktualizace stavového řádku.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|Zobrazit|Umožňuje přidání položky do sady nástrojů.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|Data|Odešle oznámení o změnách upravený soubor. (Toto rozhraní je volitelný.)|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Data|Použít k povolení této funkce Uložit jako pro určitý typ souboru.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Data|Povolí zachování dokumentu. Soubory jen pro čtení, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SetDocDataReadOnly%2A> zajistit ikonu "zamknout", který označuje soubory jen pro čtení.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|Data|Určuje, zda změny dat dokumentu třeba ji ignorovat.|