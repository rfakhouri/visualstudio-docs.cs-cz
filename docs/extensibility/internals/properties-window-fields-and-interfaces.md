---
title: Vlastnosti – okno pole a rozhraní | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, fields and interfaces
ms.assetid: 0328f0e5-2380-4a7a-a872-b547cb775050
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a286d8cc782305b746789f56af431d7a62f8e2fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="properties-window-fields-and-interfaces"></a>Vlastnosti – okno pole a rozhraní
Model pro výběr k určení, které informace se zobrazují v **vlastnosti** okno je založena na okno, který má právě fokus v prostředí IDE. Objekt kontextu jeho výběru nabídnutých do kontextu globální výběr mohou mít každý okno a objekt v rámci vybrané okno. Při toto okno je aktivní prostředí aktualizuje kontext globální výběr hodnotami z rámce okna. Když se změní fokus, takže nemá kontext výběr.  
  
## <a name="tracking-selection-in-the-ide"></a>Výběr sledování v prostředí IDE  
 Rámec okna nebo lokality, vlastníkem IDE, má služba s názvem <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>. Následující kroky ukazují, jak změnu ve výběru, způsobené uživatele změna fokus na další otevřete okno nebo vyberte jiný projekt položky v **Průzkumníku**, je implementována do zobrazený v obsah **Vlastnosti** okno.  
  
1.  Objekt vytvořený vaší VSPackage, který je umístěný ve vybrané okno pro volání <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> tak, aby měl <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> vyvolání <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  Výběr kontejner, poskytuje vybrané okno vytvoří vlastní <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> objektu. Při výběru změny VSPackage volá <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> upozornit všechny moduly pro naslouchání v prostředí, včetně **vlastnosti** okno změny. Poskytuje také přístup k informacím o hierarchii a položky související s nový výběr.  
  
3.  Volání metody <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> a předání položky vybrané hierarchie v `VSHPROPID_BrowseObject` parametr naplní <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> objektu.  
  
4.  Objekt odvozené z [IDispatch – rozhraní](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) se vrátí pro <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> pro požadovanou položku a prostředí zabalí do <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> (viz následující krok). Pokud volání selže, prostředí zavolá druhý `IVsHierarchy::GetProperty`, předání kontejneru výběr <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> , zadejte pro vybrané položky v hierarchii.  
  
     Projekt VSPackage nevytvoří <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> protože okna zadané prostředí VSPackage, která se implementuje (například **Průzkumníku řešení**) vytvoří <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> jeho jménem.  
  
5.  Prostředí vyvolá <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> získat objekty podle `IDispatch` rozhraní vyplnit **vlastnosti** okno.  
  
 Když je hodnota v **vlastnosti** okno mění, implementovat VSPackages `IVsTrackSelectionEx::OnElementValueChangeEx` a `IVsTrackSelectionEx::OnSelectionChangeEx` nahlásit změnu na hodnotu elementu. Prostředí poté vyvolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> nebo <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> zachovat informace zobrazené v **vlastnosti** okno synchronizovat se službou hodnoty vlastností. Další informace najdete v tématu [aktualizaci hodnot vlastností v okně vlastností](#updating-property-values-in-the-properties-window).  
  
 Kromě výběr jiné projektu položky v **Průzkumníku řešení** vlastnosti týkající se této položky zobrazíte můžete také zvolit jiný objekt z v rámci okna formuláře nebo dokumentu pomocí k dispozici v rozevíracím seznamu **Vlastnosti** okno. Další informace najdete v tématu [seznam objektů okno Vlastnosti](../../extensibility/internals/properties-window-object-list.md).  
  
 Můžete změnit způsob informace se zobrazují v **vlastnosti** okno mřížky z abecední do kategorií, a pokud je k dispozici, můžete také otevřít stránku vlastností pro vybraný objekt kliknutím na odpovídající tlačítko na  **Vlastnosti** okno. Další informace najdete v tématu [tlačítka okno Vlastnosti](../../extensibility/internals/properties-window-buttons.md) a [stránky vlastností](../../extensibility/internals/property-pages.md).  
  
 Nakonec dolní části **vlastnosti** okno obsahuje také popis vybraném v poli **vlastnosti** okno mřížky. Další informace najdete v tématu [získávání popisy pole v okně Vlastnosti](#getting-field-descriptions-from-the-properties-window).  
  
## <a name="updating-property-values-in-the-properties-window"></a> Aktualizace hodnoty vlastností v okně vlastností
Existují dva způsoby, jak udržovat **vlastnosti** okno synchronizována s změn hodnot vlastností. První je volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> rozhraní, která poskytuje přístup k základní oddílová funkce, včetně přístupu k a vytvoření oken nástroj a dokument poskytuje prostředí. Následující kroky popisují proces synchronizace.  
  
### <a name="updating-property-values-using-ivsuishell"></a>Aktualizace hodnoty vlastností pomocí IVsUIShell  
  
#### <a name="to-update-property-values-using-the-ivsuishell-interface"></a>K aktualizaci hodnot vlastností, pomocí rozhraní IVsUIShell  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> (prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> service) kdykoli se tento VSPackages, projekty, nebo editory nutné vytvořit nebo výčet nástroje nebo dokumentu systému windows.  
  
2.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.RefreshPropertyBrowser%2A> zachovat **vlastnosti** okno synchronizována s změny vlastností pro projekt (nebo vybraný objekt se procházet podle **vlastnosti** okno) bez implementace <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> a ohlásí <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink.OnChanged%2A> události.  
  
3.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.AdviseHierarchyEvents%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.UnadviseHierarchyEvents%2A> k zahájení a zakázat v uvedeném pořadí, klientské oznámení událostí hierarchii bez nutnosti hierarchii k implementaci <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
### <a name="updating-property-values-using-iconnection"></a>Aktualizace hodnoty vlastností pomocí připojení IConnection  
 Druhý způsob zachovat **vlastnosti** okno synchronizována s změn hodnot vlastností je implementace `IConnection` na objekt umožňující připojení k označení existenci odchozí rozhraní. Pokud chcete k lokalizaci název vlastnosti, odvozovat z objektu <xref:System.ComponentModel.ICustomTypeDescriptor>. <xref:System.ComponentModel.ICustomTypeDescriptor> Implementace můžete upravit vlastnosti popisovače, vrátí hodnotu a změňte název vlastnosti. O lokalizaci popis, vytvořit atribut, která je odvozena z <xref:System.ComponentModel.DescriptionAttribute> a přepsat vlastnost Popis.  
  
#### <a name="considerations-in-implementing-the-iconnection-interface"></a>Aspekty v jeho implementaci rozhraní připojení IConnection  
  
1.  `IConnection` poskytuje přístup k dílčí objekt enumerator s <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> rozhraní. Také poskytuje přístup ke všem připojení bodu dílčí objektům, každý z které implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní.  
  
2.  Jakýkoli objekt procházet zodpovídá za implementaci <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink> událostí. **Vlastnosti** okno bude poradit pro události, nastavte prostřednictvím `IConnection`.  
  
3.  Bod připojení určuje, kolik připojení (jeden nebo více) umožňuje při implementaci <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>. Spojovací bod, který umožňuje pouze jedno rozhraní může vrátit <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> z <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.EnumConnections%2A> metoda.  
  
4.  Klienta můžete volat `IConnection` rozhraní se získat přístup k dílčí objekt enumerator s <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> rozhraní. <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> Rozhraní může být volána výčet spojovacích bodů odchozích rozhraní ID (IID).  
  
5.  `IConnection` nelze volat také se získat přístup k připojení bodu dílčí objekty s <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní pro každý odchozí IID. Prostřednictvím <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní, klient spustí nebo ukončí smyčky poradní s objekt umožňující připojení a synchronizace klienta vlastní. Klienta můžete také zavolat <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní získat objekt enumerator s <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnections> rozhraní pro připojení, která bude vědět o zobrazení výčtu.  
  
## <a name="getting-field-descriptions-from-the-properties-window"></a> Získávání popisy pole v okně Vlastnosti
V dolní části **vlastnosti** okně oblasti popis zobrazí informace související s vybranou vlastnost pole. Tato funkce je zapnutá ve výchozím nastavení. Pokud chcete skrýt pole popisu, klikněte pravým tlačítkem **vlastnosti** a klikněte na **popis**. Také zrušeno zaškrtnutí políčka vedle **popis** název v okně nabídky. Toto pole můžete zobrazit znovu podle stejných kroků k přepnutí **popis** zpět na.  
  
 Informace v poli Popis pocházejí z <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>. Každý metoda, rozhraní, třída typu coclass a tak dále může mít nelokalizované `helpstring` atribut v knihovně typů. **Vlastnosti** okno načte řetězec, ze <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo.GetDocumentation%2A>.  
  
### <a name="to-specify-localized-help-strings"></a>Chcete-li určit lokalizované řetězce nápovědy  
  
1.  Přidat `helpstringdll` atribut příkaz knihovny v knihovně typů (`typelib`).  
  
    > [!NOTE]
    >  Tento krok je nepovinný, pokud je typ knihovna do souboru objektu knihovny (.olb).  
  
2.  Zadejte `helpstringcontext` atributy pro řetězce. Můžete také zadat `helpstring` atributy.  
  
     Tyto atributy se liší od `helpfile` a `helpcontext` atributy, které jsou obsaženy v témata nápovědy skutečné chm. souboru.  
  
 Načíst informace o popis má být zobrazen pro název zvýrazněný vlastnosti **vlastnosti** okno volání <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetDocumentation2%2A> pro vlastnost, která je vybrána, zadáte požadované `lcid` atribut pro výstupní řetězec. Interně <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2> Vyhledá zadaný v souboru DLL `helpstringdll` atribut a volání `DLLGetDocumentation` u tohoto souboru .dll pomocí zadaného kontextu a `lcid` atribut.  
  
 Podpis a provádění `DLLGetDocumentation` jsou:  
  
```cpp  
STDAPI DLLGetDocumentation  
(  
   ITypeLib * /* ptlib */,  
   ITypeInfo * /* ptinfo */,  
   LCID /* lcid */,  
   DWORD dwCtx,  
   BSTR * pbstrHelpString  
);  
```  
  
 `DLLGetDocumentation` Funkce musí být exportu definované v souboru .def pro knihovnu DLL.  
  
 Interně je vytvořen soubor .olb, který je ve skutečnosti knihovny DLL. Tuto knihovnu DLL obsahuje jeden prostředek, soubor typu knihovny (.tlb) a jeden exportované funkce, `DLLGetDocumentation`.  
  
 V případě .olb soubory `helpstringdll` atribut je volitelný, protože je stejný soubor, který obsahuje samotném souboru .tlb.  
  
 Získat řetězce objeví v **popisy** podokně, proto je nutné provést minimální je zadejte `helpstring` atribut v knihovně typů. Pokud chcete tyto řetězce lokalizovat, budete muset určit `helpstringdll` (volitelné) atribut a `helpstringcontext` (povinné) atribut a implementujte `DLLGetDocumentation`.  
  
 Neexistují žádné další rozhraní, které musí provést při získávání lokalizované informace prostřednictvím idl na `helpstringcontext` atribut a `DLLGetDocumentation`.  
  
 Jiný způsob, jak získat lokalizovaný název a popis vlastnosti je implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.GetLocalizedPropertyInfo%2A>. Další informace týkající se implementace této metody naleznete v tématu [pole okno Vlastnosti a rozhraní](../../extensibility/internals/properties-window-fields-and-interfaces.md).  

## <a name="see-also"></a>Viz také  
 [Rozšíření vlastností](../../extensibility/internals/extending-properties.md)