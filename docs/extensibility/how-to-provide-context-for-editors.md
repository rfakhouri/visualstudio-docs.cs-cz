---
title: 'Postupy: Zadejte kontext pro editory | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - provide context
ms.assetid: 12df4d06-df6b-4eaf-a7bf-c83655a0c683
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ac6880d50f7e56b63f54c627726c3339028d519e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-provide-context-for-editors"></a>Postupy: Zadejte kontext pro editory
Pro editor kontext je aktivní jenom v případě, že editoru aktivní nebo měl fokus bezprostředně před fokus byla přesunuta do okno nástroje. Pomocí následujícího postupu můžete zadat kontextu editoru:  
  
1.  Vytvořte kontejner kontextu.  
  
2.  Publikujte kontejneru kontextu identifikátor elementu výběr (SEID).  
  
3.  Udržujte kontextu, ve kontejneru.  
  
 Tyto úlohy jsou zahrnuty následující postupy. Další informace o zajišťování kontextu najdete v tématu **robustní programování** dál v tomto tématu.  
  
### <a name="to-create-a-context-bag-for-an-editor-or-a-designer"></a>Chcete-li vytvořit kontejner kontext pro editor nebo návrháře  
  
1.  Volání `QueryService` na vaše <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.SVsMonitorUserContext> služby.  
  
     Ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext> rozhraní je vrácen.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext.CreateEmptyContext%2A> metodu pro vytvoření nového kontejneru kontext nebo dílčí kontext.  
  
     Ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> rozhraní je vrácen.  
  
3.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> metodu pro přidání do kontejneru objektů a dat kontext nebo dílčí kontext atributy, klíčová slova pro vyhledávání nebo klíčová slova F1.  
  
4.  Pokud chcete vytvořit kontejner dílčí kontext, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddSubcontext%2A> metoda propojení s nadřazenou kontextu kontejner objektů a dat kontejneru dílčí kontext.  
  
5.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> pro příjem oznámení při **dynamické nápovědy** okno je aktualizovat.  
  
     S **dynamické nápovědy** okno volání jako editor když je připravena aktualizovat vám dává možnost zpoždění Změna kontextu, dokud nedojde k aktualizaci. To může zlepšit výkon, protože umožňuje zpoždění spuštění časově náročné algoritmy, dokud je k dispozici doba nečinnosti systému.  
  
### <a name="to-publish-the-context-bag-to-the-seid"></a>Publikování kontextu kontejneru SEID  
  
1.  Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> služby vrátit ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> rozhraní.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>, určující identifikátor elementu (`elementid` parametr) hodnotu SEID_UserContext indikující, že se předává kontext na globální úrovni.  
  
3.  Když stane aktivní editor nebo návrháři, hodnoty v jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> objekt rozšířeny globální výběr. Potřebujete jenom jednou za relace tento proces dokončit a potom uložte má ukazatel na globálním kontextu vytvoří, když jste volali metodu <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>.  
  
### <a name="to-maintain-the-context-bag"></a>Chcete-li zachovat kontejneru kontextu  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> zajistit, aby **dynamické nápovědy** okno volá editor nebo designer předtím, než se aktualizuje.  
  
     Pro každý kontejner kontext, který volal <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> po vytvoření kontejneru kontextu a implementovala <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>, volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> oznámit zprostředkovatele kontextu aktualizují kontejneru kontextu. Toto volání můžete změnit atributy a klíčová slova v kontextu kontejneru a v žádné dílčí kontext sáčky, než **dynamické nápovědy** Probíhá aktualizace okna.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A> na kontejner objektů a dat kontext k označení, že editor nebo designer je nový kontext.  
  
     Když **dynamické nápovědy** okno volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> označíte, že se aktualizuje, editor nebo designer můžete aktualizovat kontext pro kontejner objektů a dat nadřazené kontextu a žádné dílčí kontext sáčků v daném čase.  
  
    > [!NOTE]
    >  `SetDirty` Příznak je automaticky nastavený na `true` vždy, když je kontextu přidat nebo odebrat z kontejneru kontextu. **Dynamické nápovědy** okno pouze volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> na kontejneru kontextu Pokud `SetDirty` je příznak nastaven na `true`. Se resetují na `false` po aktualizaci.  
  
3.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> Přidat kontext active kontextu kolekce nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A> odebrat kontextu.  
  
## <a name="robust-programming"></a>Robustní programování  
 Pokud píšete vlastní editor, je třeba provést všechny tři postupy v tomto tématu, poskytují kontext pro editor.  
  
> [!NOTE]
>  Chcete-li správně aktivovat okno s editor nebo designer a zajistěte, aby směrování příkazů aktualizovala správně, musí volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> na komponentu aby okno fokus.  
  
 SEID je kolekce vlastností, které mění podle výběru. SEID informace jsou k dispozici prostřednictvím globální výběr. Globální výběr přes drátové sítě do události aktivované <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> rozhraní, a seznam všechno, co je vybráno (aktuální editor, aktuální okno nástroje, aktuální hierarchii a tak dále).  
  
 Editory a návrhářů v kontextu, které můžete kdykoli změnit kurzor se přesune do slova, je neefektivní neustále aktualizovat kontejneru kontextu. Chcete-li aktualizaci efektivnější kdykoli zjistit kurzor pohybující se v rámci editor nebo návrháře okna, můžete volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>. Tato funkce umožňuje podržte kontextové změny, dokud je čas nečinnosti a rozhraní IDE kontextu služby odesílá oznámení pro editor nebo designer, který **dynamické nápovědy** okno se aktualizuje. Tento postup se používá v postupu "postup udržovat kontejneru kontextu" v tomto tématu.  
  
 Po zadání kontextu aktivity v rámci editor nebo návrháři, měl by poskytnout konkrétní klíčové slovo F1 aby uživatelé pro získání nápovědy pro editor nebo Návrhář sám sebe.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx>