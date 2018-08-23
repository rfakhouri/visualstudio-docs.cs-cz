---
title: 'Postupy: Přidání standardní Text značky | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - standard text markers
ms.assetid: a39fca69-0014-474c-933f-51f0e9b9617e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 41232fab8545fcd0ed65c039969e40b03e754d2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696488"
---
# <a name="how-to-add-standard-text-markers"></a>Postupy: Přidání standardní Text značky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: Přidání standardní Text značky](https://docs.microsoft.com/visualstudio/extensibility/how-to-add-standard-text-markers).  
  
Pomocí následujícího postupu vytvořte jeden výchozí typ značky text, opatřeného [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základní editor.  
  
### <a name="to-create-a-text-marker"></a>Chcete-li vytvořit text značky  
  
1.  V závislosti na tom, zda používáte jeden nebo dva - multidimenzionálním souřadnicový systém, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metodu pro vytvoření nové značky text.  
  
     Při volání této metody určete typ značky, rozsah textu pro vytvoření značky nad a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní. Tato metoda pak vrací ukazatel na nově vytvořený text značky. Typy značek pocházejí ze <xref:Microsoft.VisualStudio.TextManager.Interop.MARKERTYPE> výčtu. Zadejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní, pokud chcete být informováni o událostech.  
  
    > [!NOTE]
    >  Vytvoření textu značky na pouze hlavní vlákno uživatelského rozhraní. Základní editor spoléhá na obsah vyrovnávací paměť textu pro vytvoření textu značek a textovou vyrovnávací paměť není bezpečné pro vlákna.  
  
## <a name="adding-a-custom-command"></a>Přidání vlastní příkaz.  
 Implementace `IVsTextMarkerClient` rozhraní a poskytuje ukazatel na ni z značku zlepšuje chování značky několika způsoby. Nejprve díky tomu můžete zajistit tipy pro vaši značku a příkazy. To vám také umožní příjem oznámení o události pro jednotlivé značky a vytvářet vlastní místní nabídky přes značky. Pomocí následujícího postupu přidejte vlastní příkaz na místní nabídku značky.  
  
#### <a name="to-add-a-custom-command-to-the-context-menu"></a>Chcete-li přidat vlastní příkaz do kontextové nabídky  
  
1.  Před zobrazením v místní nabídce prostředí volá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetMarkerCommandInfo%2A> – metoda a předá je ukazatel na text značky vliv a počet položky příkazu v místní nabídce.  
  
     Například obsahovat příkazů specifických pro zarážku v místní nabídce **odebrat zarážku** prostřednictvím **Nová zarážka**, jako je zobrazena na následujícím snímku obrazovky.  
  
     ![Místní nabídka značky](../extensibility/media/vsmarkercontextmenu.gif "vsMarkercontextmenu")  
  
2.  Předávání zpátky nějaký text rozlišujícího názvu vlastní příkaz. Například **odebrat zarážku** může být vlastní příkaz, pokud prostředí už neposkytl ho. Můžete také předat zpět Určuje, zda je příkazu podporované, zpřístupnění a povolení a přepínání zapnutí nebo vypnutí. Prostředí používá tyto informace k zobrazení vlastního příkazu v místní nabídce správným způsobem.  
  
3.  Ke spuštění příkazu prostředí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> metoda předání ukazatele text značky a počet vybraný v místní nabídce příkaz.  
  
     Tyto informace z tohoto volání použijte k provedení libovolné akce text značky určuje vlastní příkaz.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: implementace označování chyb](../extensibility/how-to-implement-error-markers.md)   
 [Postupy: vytvoření vlastního textu značky](../extensibility/how-to-create-custom-text-markers.md)   
 [Postupy: použití značek Text](../extensibility/how-to-use-text-markers.md)

