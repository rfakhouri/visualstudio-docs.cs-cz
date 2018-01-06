---
title: "Nové nebo změněné chování Editor adaptéry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - adapter behavior
ms.assetid: 5555b116-cfdb-4773-ba62-af80fda64abd
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c24b8c5520befcc204b59609b116d9d16ee26281
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="new-or-changed-behavior-with-editor-adapters"></a>Nové nebo změněné chování adaptéry editoru
Pokud aktualizujete kód, který byl napsaných pro starší verze sady Visual Studio základní editoru a máte v úmyslu použít editor adaptérů (nebo překrytí) místo pomocí nového rozhraní API, byste měli vědět následující rozdíly v chování nástroje adaptéry editoru s ohledem na předchozí základní editor.  
  
## <a name="features"></a>Funkce  
  
#### <a name="using-setsite"></a>Pomocí SetSite()  
 Je třeba volat <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite.SetSite%2A> při vytvořit textové vyrovnávací paměti, zobrazení textu a kódu windows, před provedením další operace s nimi. Je to ale není nutné v případě, že používáte <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> vytvořit, protože volání metody Create() této služby, sami <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.SetSite%2A>.  
  
#### <a name="hosting-ivscodewindow-and-ivstextview-in-your-own-content"></a>Hostování IVsCodeWindow a IVsTextView v svůj vlastní obsah  
 Je možné hostovat obě <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> vlastní obsah pomocí Win32 režim nebo režim WPF. Nicméně byste měli mít na paměti, že jsou některé rozdíly ve dvou režimech.  
  
##### <a name="using-win32-and-wpf-versions-of-ivscodewindow"></a>Použití Win32 a WPF verzí IVsCodeWindow  
 Okno editoru kódu je odvozený od <xref:Microsoft.VisualStudio.Shell.WindowPane>, které implementuje starší Win32 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní a také nové WPF <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> rozhraní. Můžete použít <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsWindowPane%23CreatePaneWindow%2A> metodu pro vytvoření na základě HWND hostování prostředí, nebo <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsUIElementPane%23CreateUIElementPane%2A> metodu pro vytvoření hostitelského prostředí WPF. Základní editor vždy používá WPF, ale můžete vytvořit druh podokna, který vyhovuje požadavků na hostování, pokud v tomto podokně okna jsou vložení přímo do vlastní obsah.  
  
##### <a name="using-win32-and-wpf-versions-of-ivstextview"></a>Použití Win32 a WPF verzí IVsTextView  
 Můžete nastavit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 režim nebo režim WPF.  
  
 Pokud objekt factory editoru vytvoří textového zobrazení, ve výchozím nastavení je umístěn uvnitř popisovačem HWND a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> vrací HWND. Tento režim byste neměli používat pro vložení editoru uvnitř ovládací prvek WPF.  
  
 Nastavit na režim WPF textového zobrazení, musí volat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.Initialize%2A> a předat <xref:Microsoft.VisualStudio.TextManager.Interop.TextViewInitFlags3> jako jeden z inicializace flags v `InitView` parametr. Můžete získat <xref:System.Windows.FrameworkElement> voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane.CreateUIElementPane%2A>.  
  
 WPF režimu se liší od režimu Win32 dvěma způsoby. Nejprve textového zobrazení může být hostovaný v kontextu WPF. V podokně WPF můžete přejít pomocí přetypování <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> k <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElement.GetUIObject%2A>. Druhý, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> stále vrátí popisovačem HWND, ale tato HWND slouží pouze k zkontrolujte jeho umístění a zaměřit se na něm. Vzhledem k tomu, že ji nebude mít vliv na to, jak editoru vybarví okna, nesmí používat tento HWND reagovat na zprávu WM_PAINT. Tato HWND není k dispozici pouze pro usnadnění přechodu na nový kód editor prostřednictvím adaptéry. Důrazně doporučujeme byste neměli používat `VIF_NO_HWND_SUPPORT` Pokud příslušné součásti vyžaduje popisovačem HWND pracovat z důvodu omezení v HWND vrácená z `GetWindowHandle` při v tomto režimu.  
  
#### <a name="passing-arrays-as-parameters-in-native-code"></a>Předávání polí jako parametrů v nativním kódu  
 Existuje mnoho způsobů v editoru starší verze rozhraní API, které mají parametry, které obsahují pole a jeho počet. Mezi příklady patří:  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.AppendViewOnlyMarkerTypes%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.RemoveViewOnlyMarkerTypes%2A>  
  
 Při volání těchto metod v nativním kódu, musí projít v pouze jeden element najednou. Pokud předáte ve více než jeden element, volání se odmítne kvůli problémům s primární spolupráce implementace.  
  
 Problém je složitější s metodami, jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetIgnoreMarkerTypes%2A>. Pokaždé, když tato metoda je volána, vymaže předchozí seznam typů ignorováno značky, takže není možné jednoduše mohli volat tuto metodu třikrát s tři typy jiné značky. Pouze remedy je mohli volat tuto metodu jenom ve spravovaném kódu.  
  
#### <a name="threading"></a>Dělení na vlákna  
 Adaptér vyrovnávací paměti by měly vždy volat z vlákna uživatelského rozhraní. Adaptér pro vyrovnávací paměť je spravovaný objekt, což znamená, že se volání do ní ze spravovaného kódu vynechat zařazování COM a volání nebude automaticky zařadit do vlákna uživatelského rozhraní.  Pokud adaptér vyrovnávací paměti se volá z vlákna na pozadí, musíte použít <xref:System.Windows.Threading.Dispatcher.Invoke%2A> nebo podobné metody.  
  
#### <a name="lockbuffer-methods"></a>LockBuffer metody  
 Všechny metody LockBuffer() jsou zastaralé. Mezi příklady patří:  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.LockBuffer%2A>  
  
#### <a name="commit-events"></a>Potvrzení události  
 Potvrzení události nejsou podporovány. Volání metody, která informuje o tom, aby se tyto události způsobí, že metoda vrátí kód chyby.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUndoRedoClusterWithCommitEvents>  
  
#### <a name="texteditorevents"></a>TextEditorEvents  
 <xref:EnvDTE.TextEditorEvents> Už fire na Commit(). Místo toho budou platit při každé změně textu.  
  
#### <a name="text-markers"></a>Text značky  
 Je třeba volat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker.Invalidate%2A> na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker> objekty, když je odebrat. V předchozích verzích je potřeba pouze na verzi značek.  
  
#### <a name="line-numbers"></a>Čísla řádků  
 Pro celou řadu metod na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>čísla řádků odpovídají základní čísla řádků vyrovnávací paměti, které hrají roli v přehledy a word-wrap, jako v sadě Visual Studio 2008 čísla řádků není.  
  
 Metody vliv patří (seznam není vyčerpávající):  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.CenterLines%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineAndColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetNearestPosition%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetPointOfLineColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetTextStream%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWordExtent%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.ReplaceTextOnLine%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetSelection%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetTopLine%2A>  
  
#### <a name="outlining"></a>Sbalování  
 Klienti v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se zobrazí pouze popisující oblasti, které byly přidány pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A>nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSessionEx.AddHiddenRegionsEx%2A>. Neuvidí ad hoc oblastech, protože nebyly přidány prostřednictvím adaptérů editor. Tito klienti, se nezobrazí osnovy oblasti přidal jazyky (včetně c a C++), které používají nový kód editor spíše než adaptéry editor.  
  
#### <a name="line-heights"></a>Výšky řádku  
 V editoru nové řádky textu může mít různé výšky, v závislosti na velikosti písma a možné řádku transformace, které může přesunout na řádku vzhledem k další řádky. Výška řádku vrácené metody, jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineHeight%2A> je height výšky řádku pomocí žádný řádek transformací použitá výchozí velikost písma. Tato výška může nebo nemusí odrážet skutečné height výšky řádku v zobrazení.  
  
#### <a name="eventing-and-undo"></a>Zpracování událostí a vrácení zpět  
 V editoru nové zobrazení nadále provádět operace, jako je například vykreslování a vyvolávání událostí nepřetržitě, i v případě, že cluster služby vrácení zpět je otevřený. Toto chování se liší od starších verzí zobrazení, která není provedli tyto operace až po zavření clusteru vrácení zpět.  
  
#### <a name="intellisense"></a>IntelliSense  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateTipWindow%2A> Metoda se nezdaří, pokud je předat ve třídě, která buď neimplementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextTipWindow2> nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow3>. Vlastní Win32 vykreslovaných vlastníkem automaticky otevíraná okna jsou již není podporována.  
  
#### <a name="smarttags"></a>Inteligentní značky  
 Neexistuje žádná podpora adaptéru pro inteligentní značky vytvořené, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagData>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow>, a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow2> rozhraní.  
  
#### <a name="dte"></a>DTE  
 <xref:EnvDTE80.IncrementalSearch>není implementováno.  
  
## <a name="unimplemented-methods"></a>Neimplementované metody  
 Některé metody nebyla provedena na adaptéru textové vyrovnávací paměti, adaptér zobrazení textu a text vrstvy adaptéru.  
  
|Rozhraní|Není implementováno|  
|---------------|---------------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|`Reload(false)`není implementováno.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.EnumSpans%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetBufferMappingModes%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.ReleaseMarkerData%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CanReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CopyLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.EnumLayerMarkers%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetBaseBuffer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLengthOfLine%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineCount%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.LockBufferEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.MapLocalSpansToTextOriginatingLayer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReleaseMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLinesEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.UnlockBufferEx%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView.GetSelectedAtom%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetSelectionDataObject%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RestrictViewRange%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateViewFrameCaption%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.InvokeInsertionUI%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetHoverWaitTimer%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetViewClassID%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.AfterCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.BeforeCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetContextLocation%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetServiceProvider%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.ReplaceSubjectTextSpan%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateSmartTagWindow%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost.SetSubjectFromPrimaryBuffer%2A>je implementována, adaptérů, ale ignoruje podle osnovy uživatelského rozhraní.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx.GetBannerAttr%2A>je implementována, adaptérů, ale ignoruje podle osnovy uživatelského rozhraní.|