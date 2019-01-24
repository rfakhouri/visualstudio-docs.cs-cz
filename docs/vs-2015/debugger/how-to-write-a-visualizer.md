---
title: 'Postupy: Zápis Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, writing
ms.assetid: 625a0d4f-abcc-43f2-9f8c-31c131a4378e
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2421121e343fabbe3f2ec7d88ec087c6b84c8709
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766458"
---
# <a name="how-to-write-a-visualizer"></a>Postupy: Zápis Vizualizéru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete napsat vlastní vizualizér pro všechny spravované třídy s výjimkou objektu <xref:System.Object> nebo <xref:System.Array>.  
  
> [!NOTE]
>  V **Store** aplikací, jenom standardní text, HTML, XML a JSON vizualizéry jsou podporovány. Vizualizéry vlastní (uživatelem vytvořené) nejsou podporovány.  
  
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
  
  Následující postupy poskytnout souhrnný přehled, co je potřeba provést k vytvoření vizualizéru. Podrobnější vysvětlení najdete v tématu [názorný postup: Zápis Vizualizéru v C# ](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
### <a name="to-create-the-debugger-side"></a>Chcete-li vytvořit vedlejší ladicího programu  
  
1.  Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> metody k získání vizualizovanému objektu na straně ladicího programu.  
  
2.  Vytvořte třídu, která dědí z <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>.  
  
3.  Přepsat <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> metodu pro zobrazení rozhraní. Použití <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> metody k zobrazení formuláře Windows, dialogová okna a ovládací prvky jako součást rozhraní.  
  
4.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, že mu poskytneme vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>).  
  
### <a name="to-create-the-debuggee-side"></a>Chcete-li vytvořit na straně laděného procesu  
  
1.  Použít <xref:System.Diagnostics.DebuggerVisualizerAttribute>, že mu poskytneme vizualizéru (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>) a objektový zdroj (<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>). Vynecháte-li objektový zdroj, použije se výchozí objekt zdroj  
  
2.  Pokud chcete vaše vizualizéru být schopni upravit datové objekty, stejně jako zobrazované, budete muset přepsat `TransferData` nebo `CreateReplacementObject` metody ze <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)   
 [Postupy: Instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Postupy: Testování a ladění Vizualizéru](../debugger/how-to-test-and-debug-a-visualizer.md)   
 [Informace o zabezpečení vizualizéru](../debugger/visualizer-security-considerations.md)
