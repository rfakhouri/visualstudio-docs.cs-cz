---
title: Vytváření vlastních Vizualizérů dat | Dokumentace Microsoftu
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
ms.openlocfilehash: 859bf6493a06663a8977898ffa07d600b826d458
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854309"
---
# <a name="create-custom-visualizers-of-data"></a>Vytváření vlastních Vizualizérů dat
 Vizualizéry jsou součástí [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] uživatelské rozhraní ladicího programu. A *vizualizéru* vytvoří dialogové okno nebo jiné rozhraní pro zobrazení proměnné nebo objektu způsobem, který je vhodný k jeho datovému typu. Například HTML vizualizér interpretuje řetězec ve formátu HTML a výsledek zobrazí, jak se bude zobrazovat v okně prohlížeče; rastrový obrázek vizualizéru interpretuje struktura rastrový obrázek a zobrazí obrázek, který představuje. Některé vizualizéry umožňují snadno změnit také zobrazit data.

 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] Ladicí program obsahuje šest standardní vizualizéry. Toto jsou text, HTML, XML a JSON vizualizátory, nástroje pro všechny z nich pracovat na řetězcových objektů; vizualizéru stromu WPF, pro zobrazení vlastností objektu WPF vizuálního stromu; a vizualizér datasetu, který se dá použít pro objekty datové sady, zobrazení dat a DataTable. Další vizualizéry může být v budoucnosti k dispozici ke stažení od společnosti Microsoft a jsou k dispozici od třetích stran a komunity. Kromě toho můžete napsat vlastní vizualizéry a nainstalovat je do [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ladicího programu.

 > [!NOTE]
 > Pokud chcete vytvořit vlastní vizualizér pro nativní kód, naleznete v tématu [nativní vizualizér SQLite](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/SqliteVisualizer) vzorku. V aplikacích UPW a Windows 8.x nejsou podporovány vlastní vizualizéry.

 V ladicím programu, vizualizéry jsou reprezentovány s ikonou lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Vizualizéru ikonu"). Když se zobrazí ikona lupy v **datového tipu**, v okně ladicího programu, jako je **Watch** okna, nebo v **QuickWatch** dialogové okno, můžete kliknout na ikonu lupy Vyberte odpovídající datový typ odpovídající objekt vizualizéru.

## <a name="overview-of-custom-visualizers"></a>Přehled vlastních vizualizérech

Můžete napsat vlastní vizualizér pro všechny spravované třídy s výjimkou objektu <xref:System.Object> nebo <xref:System.Array>.  
  
 Architektura vizualizéru ladicí program má dvě části:  
  
- *Ladicího programu na straně* běží v rámci ladicího programu sady Visual Studio. Ladicí program na straně kód vytvoří a zobrazí uživatelské rozhraní pro vaše vizualizér.  
  
- *Na straně laděného procesu* běží v rámci procesu ladění sady Visual Studio ( *laděného procesu*).  
  
  Datový objekt, který chcete vizualizovat (objekt String, například) neexistuje v laděném procesu. K odeslání dat objektu na stranu ladicí program, který potom můžete zobrazit pomocí uživatelského rozhraní, které vytvoříte, má na straně laděného procesu.  
  
  Na straně ladicí program přijímá tímto datovým objektem. Chcete-li vizualizovat z *zprostředkovatele objektu* , který implementuje <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> rozhraní. Na straně laděného procesu odešle datový objekt prostřednictvím *zdroj objektu*, který je odvozen z <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>. Objekt zprostředkovatele můžete také odeslat data zpět do zdroje objektu, která umožňuje zápis vizualizéru, který upravuje, jakož i zobrazí, data. Zprostředkovatele objektu může být potlačena za účelem mluvit vyhodnocovací filtr výrazů a proto zdrojového objektu  
  
  Na straně laděného procesu a ladicí program na straně mezi sebou komunikovat prostřednictvím <xref:System.IO.Stream>. Metody jsou k dispozici k serializaci dat objektů do <xref:System.IO.Stream> a deserializaci <xref:System.IO.Stream> zpět do datového objektu.  
  
  Kód na straně laděného procesu je zadán pomocí atributu DebuggerVisualizer (<xref:System.Diagnostics.DebuggerVisualizerAttribute>).  
  
  K vytvoření vizualizátor uživatelského rozhraní na straně ladicího programu, je nutné vytvořit třídu, která dědí z <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> a přepsat <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> metodu pro zobrazení rozhraní.  
  
  Můžete použít <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> k zobrazení formuláře Windows, dialogová okna a ovládací prvky z vašich vizualizér.  
  
  Podpora pro obecné typy je omezená. Můžete napsat vizualizér pro cíl, který je obecný typ, pouze pokud je otevřený typ obecného typu. Toto omezení je stejné jako omezení při použití `DebuggerTypeProxy` atribut. Podrobnosti najdete v tématu [používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md).  
  
  Důležité informace o zabezpečení může mít vlastní vizualizéry. Zobrazit [hlediska zabezpečení Vizualizéru](../debugger/visualizer-security-considerations.md).  
  
  Následující postupy poskytnout souhrnný přehled, co je potřeba provést k vytvoření vizualizéru. Podrobnější vysvětlení najdete v tématu [návod: zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
### <a name="to-create-the-debugger-side"></a>Chcete-li vytvořit vedlejší ladicího programu  
  
1.  Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> metody k získání vizualizovanému objektu na straně ladicího programu.  
  
2.  Vytvořte třídu, která dědí z <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>.  
  
3.  Přepsat <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> metodu pro zobrazení rozhraní. Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> metody k zobrazení formuláře Windows, dialogová okna a ovládací prvky jako součást rozhraní.  
  
4.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, že mu poskytneme vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>).  
  
### <a name="to-create-the-debuggee-side"></a>Chcete-li vytvořit na straně laděného procesu  
  
1.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, že mu poskytneme vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>) a objektový zdroj (<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>). Vynecháte-li objektový zdroj, použije se výchozí objekt zdroj  
  
2.  Pokud chcete vaše vizualizéru být schopni upravit datové objekty, stejně jako zobrazované, budete muset přepsat `TransferData` nebo `CreateReplacementObject` metody ze <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>.   
  
## <a name="in-this-section"></a>V tomto oddílu
  
 [Návod: Zápis vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  

 [Návod: Zápis vizualizéru v jazyce Visual Basic](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)  
  
 [Postupy: Instalace vizualizéru](../debugger/how-to-install-a-visualizer.md)  
  
 [Postupy: Testování a ladění vizualizéru](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [Referenční dokumentace k rozhraní API vizualizéru](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>Související oddíly  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)