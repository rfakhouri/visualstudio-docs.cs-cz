---
title: Vytvořit vlastní Vizualizérech dat | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.visualizer.troubleshoot
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2a1602808cb21bd247d2bb1d249ab7ddea81524
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464833"
---
# <a name="create-custom-visualizers-of-data"></a>Vytvořit vlastní Vizualizérech dat
 Vizualizérech jsou součástí [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ladicí program uživatelské rozhraní. A *vizualizér* vytvoří dialogové okno nebo jiné rozhraní k zobrazení proměnné nebo objekt způsobem, který je vhodný pro jeho datového typu. Například HTML vizualizér interpretuje řetězec HTML a výsledek zobrazí, jako by se zobrazí v okně prohlížeče; Vizualizér rastrový obrázek interpretuje strukturu rastrového obrázku a zobrazí obrázek, který představuje. Některé vizualizérech umožňují upravit a také zobrazit data.

 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] Ladicí program obsahuje šest standardní vizualizérech. Toto jsou text, HTML, XML a JSON vizualizérech, což pracovat na řetězec objekty; vizualizéru stromu WPF, pro zobrazení vlastností objektu WPF vizuálního stromu; a vizualizér datasetu, který funguje pro datovou sadu, zobrazení dat a DataTable objekty. Další vizualizérech může být k dispozici ke stažení od Microsoft Corporation v budoucnosti a jsou dostupné z jiných výrobců a její komunitě. Kromě toho můžete napsat vlastní vizualizérech a nainstalovat je [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ladicí program.

 > [!NOTE]
 > Pokud chcete vytvořit vlastní vizualizér pro nativní kód, najdete v části [SQLite nativní ladicí program vizualizér](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/SqliteVisualizer) ukázka. V aplikacích UWP a Windows 8.x vlastní vizualizérech nejsou podporovány.

 V ladicím programu, jsou vizualizérech reprezentované ikonou lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "vizualizér ikonu"). Až se zobrazí na ikonu lupy v **popis dat**, v okně ladicí program jako **sledovat** okno, nebo v **QuickWatch** dialogové okno, můžete kliknout na lupy na Vyberte odpovídající datový typ odpovídající objekt vizualizéru.

## <a name="overview-of-custom-visualizers"></a>Přehled vlastní vizualizérech

Můžete napsat vlastní vizualizér pro objekt žádné spravované třídě s výjimkou <xref:System.Object> nebo <xref:System.Array>.  
  
 Architektura vizualizéru ladicí program má dvě části:  
  
-   *Ladicího programu straně* běží v ladicím programu sady Visual Studio. Ladicí program na straně kód vytvoří a zobrazí uživatelské rozhraní pro vaše vizualizér.  
  
-   *Pozastaven straně* běží v procesu je ladění v sadě Visual Studio ( *pozastaven*).  
  
 Datový objekt, který chcete vizualizovat (objekt String, např.) existuje v pozastaven procesu. Ano na straně pozastaven má k odeslání dat objektu na straně ladicí program, který pak můžete zobrazit pomocí uživatelského rozhraní, které vytvoříte.  
  
 Tento datový objekt k vizualizovat z obdrží straně ladicí program *zprostředkovatele objektu* , která implementuje <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> rozhraní. Na straně pozastaven odešle datový objekt prostřednictvím *zdroj objektu*, který je odvozen z <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>. Objekt zprostředkovatele může také odesílat data zpět do zdroje objektu, která umožňuje zápis vizualizéru, která upraví a také zobrazuje, data. Zprostředkovatele objektu může být potlačena za účelem komunikovat vyhodnocovací filtr výrazů a proto zdrojového objektu  
  
 Na straně pozastaven a ladicí program straně vzájemnou komunikaci prostřednictvím <xref:System.IO.Stream>. Metody jsou k dispozici k serializaci objektu dat do <xref:System.IO.Stream> a deserializaci <xref:System.IO.Stream> zpět do datového objektu.  
  
 Kód pozastaven straně je určen pomocí atributu DebuggerVisualizer (<xref:System.Diagnostics.DebuggerVisualizerAttribute>).  
  
 Pokud chcete vytvořit vizualizér uživatelského rozhraní na straně ladicí program, je nutné vytvořit třídu, která dědí z <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> a přepsat <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> metodu pro zobrazení rozhraní.  
  
 Můžete použít <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> k zobrazení, formulářů, dialogů a ovládacích prvků z vaší vizualizér systému Windows.  
  
 Podpora pro obecné typy je omezená. Můžete napsat vizualizér pro cíl, který je obecný typ. pouze v případě, že je otevřený typ obecného typu. Toto omezení je stejné jako omezení při použití `DebuggerTypeProxy` atribut. Podrobnosti najdete v tématu [pomocí atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md).  
  
 Vlastní vizualizérech může mít důležité informace o zabezpečení. V tématu [hlediska zabezpečení Vizualizéru](../debugger/visualizer-security-considerations.md).  
  
 Podle pokynů níže, poskytnout podrobný pohled co musíte udělat k vytvoření vizualizéru. Podrobnější vysvětlení najdete v tématu [návod: zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
### <a name="to-create-the-debugger-side"></a>Chcete-li vytvořit na straně ladicí program  
  
1.  Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> metody pro získání vizualizovaných objektu na straně ladicí program.  
  
2.  Vytvořte třídu, která dědí z <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>.  
  
3.  Přepsání <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> metodu pro zobrazení vaše rozhraní. Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> způsoby, jak zobrazit jako součást vaší rozhraní Windows forms, dialogová okna a ovládací prvky.  
  
4.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, která poskytuje vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>).  
  
### <a name="to-create-the-debuggee-side"></a>Chcete-li vytvořit na straně pozastaven  
  
1.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, která poskytuje vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>) a zdroj objektu (<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>). Pokud vynecháte zdroj objektu, se použije výchozí objekt zdroj  
  
2.  Pokud chcete, aby vaše vizualizér mohli upravit datových objektů, stejně jako zobrazit, budete muset přepsat `TransferData` nebo `CreateReplacementObject` metody z <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>.   
  
## <a name="in-this-section"></a>V tomto oddílu
  
 [Návod: Zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  

 [Návod: Zápis Vizualizéru v jazyce Visual Basic](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)  
  
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)  
  
 [Postupy: testování a ladění Vizualizéru](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [Referenční dokumentace rozhraní API vizualizéru](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>Související oddíly  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)