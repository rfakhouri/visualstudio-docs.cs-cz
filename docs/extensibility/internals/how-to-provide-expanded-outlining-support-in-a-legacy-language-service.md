---
title: Zadejte vymezující podporu ve službě jazyk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], outlining support
- language services, supporting outlining
- outlining, supporting
ms.assetid: df759e89-8193-418c-8038-6626304d387b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6467a1e3386daedc4a67aa420c06cf01187b8d22
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-provide-expanded-outlining-support-in-a-legacy-language-service"></a>Postupy: podporují rozšířené popisující ve službě jazyk starší verze
Existují dvě možnosti pro rozšíření osnovy podporu pro svůj jazyk nad rámec podpora **sbalit do definice** příkaz. Můžete přidat oblasti řízenou editor osnovy a přidat oblasti osnovy řízenou klienta.  
  
## <a name="adding-editor-controlled-outline-regions"></a>Přidání oblasti řízenou Editor osnovy  
 Tuto metodu použijte k vytvoření oblast outline a potom povolit editoru pro zpracování, zda je rozbalený oblast, sbalené a tak dále. Z následujících dvou možností pro zajištění podpory popisující tato možnost je nejmíň robustní. Pro tuto možnost vytvoříte novou oblast outline přes dané rozpětí text použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>. Po vytvoření této oblasti své chování řídí editoru. Implementace oblasti řízenou editor osnovy pomocí následujícího postupu.  
  
#### <a name="to-implement-an-editor-controlled-outline-region"></a>K implementaci oblast řízené editor obrysu  
  
1.  Volání `QueryService` pro <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>  
  
     Tento příkaz vrátí ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>a předejte ukazatel pro danou textovou vyrovnávací paměť. Tento příkaz vrátí ukazatel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> objekt pro vyrovnávací paměť.  
  
3.  Volání <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> pro ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession>.  
  
4.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> můžete přidat jeden nebo více nových popisují oblasti najednou.  
  
     Tato metoda umožňuje zadat rozpětí textu outline, jestli jsou existující oblasti osnovy odebrat nebo zachována a zda je oblast outline rozbalit nebo sbalit ve výchozím nastavení.  
  
## <a name="adding-client-controlled-outline-regions"></a>Přidání oblasti řízenou klienta osnovy  
 Použijte tento přístup k implementace řízenou klienta (nebo inteligentní) vymezující jako používaného [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] jazykových služeb. Služba jazyka, která spravuje vlastní osnovy monitoruje vyrovnávací paměti obsah textu k destroy staré oblasti osnovy, když se stává neplatným a vytvářet nové oblasti osnovy podle potřeby.  
  
#### <a name="to-implement-a-client-controlled-outline-region"></a>K implementaci klienta řízené outline oblast  
  
1.  Volání `QueryService` pro <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>. Tento příkaz vrátí ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>a předejte ukazatel pro danou textovou vyrovnávací paměť. Určuje, zda relace skrytý text, který je již existuje pro vyrovnávací paměť.  
  
3.  Pokud text relace již existuje, pak není potřeba vytvořit jednu a ukazatel na existující <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se vrátí objekt. Použijte tento ukazatel výčet a vytvářet oblasti osnovy. Jinak volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> pro vytvoření relace skrytého textu pro vyrovnávací paměť. Ukazatel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se vrátí objekt.  
  
    > [!NOTE]
    >  Při volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A>, můžete zadat klienta skrytý text (tedy <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient> objekt). Tohoto klienta, upozorní vás při skrytého textu nebo outline oblast je rozbalit nebo sbalit uživatelem.  
  
4.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> struktura) parametr: Zadejte hodnotu <xref:Microsoft.VisualStudio.TextManager.Interop.HIDDEN_REGION_TYPE> v `iType` členem <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktura indikující, že vytváříte oblast outline, nikoli Skrytá oblast. Určete, zda je oblast řízené klienta nebo editor řídí ve službě `dwBehavior` členem <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktura. Inteligentní popisující implementace může obsahovat kombinaci oblastí outline řídí editoru a klienta. Zadejte hlavičku text, který se zobrazí, když vaši oblast outline sbalena, jako je například "...", v `pszBanner` členem <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktura. Editoru výchozí banner text pro skrytý oblast je "...".