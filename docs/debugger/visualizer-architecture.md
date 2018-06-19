---
title: Architektura vizualizéru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 6aad395f-7170-4d9e-b2b8-a5faf453380e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b20572409ac49451f58584be20fbabfdab39a3ba
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31478158"
---
# <a name="visualizer-architecture"></a>Architektura vizualizéru
Architektura vizualizéru ladicí program má dvě části:  
  
-   *Ladicího programu straně* běží v ladicím programu sady Visual Studio. Ladicí program na straně kód vytvoří a zobrazí uživatelské rozhraní pro vaše vizualizér.  
  
-   *Pozastaven straně* běží v procesu je ladění v sadě Visual Studio ( *pozastaven*).  
  
 Vizualizéru je součástí ladicí program, která umožňuje ladicí program k zobrazení (*vizualizovat*) obsah objekt dat ve formuláři smysluplný, nerozumí. Některé vizualizérech podporují také úpravy datového objektu. Vytvořením vlastní vizualizérech můžete rozšířit ladicího programu pro zpracování vlastní vlastní datové typy.  
  
 Datový objekt k vizualizovat nachází v procesu, kterou ladíte ( *pozastaven* proces). Uživatelské rozhraní, které se zobrazí data se vytvoří v rámci procesu ladicího programu sady Visual Studio:  
  
|Proces ladicího programu|Pozastaven procesu|  
|----------------------|----------------------|  
|Uživatelské rozhraní (datatips –, okno kukátka QuickWatch) ladicího programu|Datový objekt k vizualizovat|  
  
 K vizualizaci dat objekt v rámci rozhraní ladicího programu, je nutné kód pro komunikaci mezi dvěma procesy. V důsledku toho architektura vizualizéru se skládá ze dvou částí: *ladicího programu straně* kódu a *pozastaven straně* kódu.  
  
 Ladicí program na straně kód vytvoří vlastní uživatelské rozhraní, který lze vyvolat pomocí rozhraní ladicího programu, například datového tipu, kukátko – okno nebo QuickWatch. Vizualizér rozhraní je vytvořená pomocí <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> třídy a <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> rozhraní. Jako všechna rozhraní API Vizualizéru, DialogDebuggerVisualizer a IDialogVisualizerService jsou součástí <xref:Microsoft.VisualStudio.DebuggerVisualizers> oboru názvů.  
  
|Straně ladicí program|Pozastaven straně|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer – třída<br /><br /> IDialogVisualizerService rozhraní|Datový objekt|  
  
 Uživatelské rozhraní získá data, která mají být vizualizována od poskytovatele objektu, která již existuje na straně ladicí program:  
  
|Straně ladicí program|Pozastaven straně|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer – třída<br /><br /> IDialogVisualizerService rozhraní|Datový objekt|  
|Objekt zprostředkovatele (implementuje <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>)||  
  
 Neexistuje odpovídající objektu na straně pozastaven názvem zdroj objektu:  
  
|Straně ladicí program|Pozastaven straně|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer – třída<br /><br /> IDialogVisualizerService rozhraní|Datový objekt|  
|Objekt zprostředkovatele (implementuje <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>)|Objekt zdroje (odvozený z <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>)|  
  
 Objekt zprostředkovatele poskytuje data objektu, která je vizualizovat k vizualizér uživatelského rozhraní. Objekt zprostředkovatel získá data objektu na zdroji objektu. Objekt zprostředkovatele a zdroj objektu poskytují rozhraní API pro data objektu na straně ladicí program až na straně debugee komunikovat.  
  
 Každý vizualizér, musíte si datový objekt k vizualizovat. Následující tabulka uvádí odpovídající rozhraní API, že pro tento účel použít zprostředkovatele objektu a zdroj objektu:  
  
|Objekt zprostředkovatele|Zdroj objektu|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A><br /><br /> —nebo—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>|  
  
 Všimněte si, zprostředkovatele objektu můžete použít buď <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> nebo <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>. Buď rozhraní API, které jsou výsledkem volání <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A> na zdroji objektu. Volání <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A?displayProperty=fullName> vyplní <xref:System.IO.Stream?displayProperty=fullName>, která představuje formuláři serializovaného objektu, který se vizualizace.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName> deserializuje data zpět do formuláře objekt, který pak můžete zobrazit v uživatelském rozhraní vytvoříte s <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> vyplní data jako raw `Stream`, které musí deserializovat sami. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName> funguje tak, že volání <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> získat serializovaný `Stream`, pak deserializaci data. Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> při objekt není serializovatelný pomocí rozhraní .NET a vyžaduje vlastní serializace. V takovém případě je nutné také přepsat <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.Serialize%2A?displayProperty=fullName> metoda.  
  
 Pokud vytváříte jen pro čtení vizualizér, jednosměrná komunikace s <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> nebo <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A> je dostačující. Pokud vytváříte vizualizér, který podporuje úpravy datových objektů, je potřeba udělat další. Musíte být schopni také odeslat datový objekt ze zprostředkovatele objektu zpět na zdroji objektu. Následující tabulka uvádí zprostředkovatele objektu a objekt zdroje rozhraní API používaná pro tento účel:  
  
|Objekt zprostředkovatele|Zdroj objektu|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A><br /><br /> —nebo—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>|  
  
 Všimněte si, že existují dvě rozhraní API, které můžete použít zprostředkovatele objektu. Vždy odeslání dat ze zprostředkovatele objektu na objekt zdroj jako `Stream`, ale <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> vyžaduje, že jste k serializaci objektu do `Stream` sami.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A> serializuje trvá na objekt, který zadáte, ho do `Stream`, pak zavolá <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> k odeslání `Stream` k <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>.  
  
 Pomocí jedné z metod nahradit vytvoří nový objekt dat v ladění, který nahrazuje objekt se detekují. Pokud chcete změnit obsah původního objektu bez jeho nahrazení, použijte jednu z metod přenosu uvedené v následující tabulce. Tato rozhraní API přenosu dat v obou směrech ve stejnou dobu, nahradit objekt, který je právě vizualizována:  
  
|Objekt zprostředkovatele|Zdroj objektu|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferData%2A><br /><br /> —nebo—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.TransferData%2A>|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md)   
 [Návod: Zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [Návod: Zápis Vizualizéru v jazyce Visual Basic](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [Návod: Zápis Vizualizéru v jazyce Visual Basic](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [Hlediska zabezpečení vizualizéru](../debugger/visualizer-security-considerations.md)