---
title: "Postupy: Přidání značek standardního textového | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - standard text markers
ms.assetid: a39fca69-0014-474c-933f-51f0e9b9617e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bdcdbabae26a9116b1e00910ecef2f83f4075551
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-standard-text-markers"></a>Postupy: Přidání značek standardního textu
Pomocí následujícího postupu vytvořit jeden z typů značky text výchozí součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor.  
  
### <a name="to-create-a-text-marker"></a>Chcete-li vytvořit značku textu  
  
1.  V závislosti na tom, jestli používáte jeden nebo dva - dimenzí souřadnicový systém, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metodu pro vytvoření nové značky text.  
  
     Toto volání metody zadejte typ značky, rozsah text, který se vytvoří značky a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní. Tato metoda vrátí ukazatel na nově vytvořený text značku. Typy značky jsou převzaty z <xref:Microsoft.VisualStudio.TextManager.Interop.MARKERTYPE> výčtu. Zadejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní, pokud chcete být informováni o událostech.  
  
    > [!NOTE]
    >  Vytvořte značek text jenom hlavní vlákna uživatelského rozhraní. Editor základní využívá obsah textová vyrovnávací paměť pro vytvoření textového značek a textová vyrovnávací paměť není bezpečné pro přístup z více vláken.  
  
## <a name="adding-a-custom-command"></a>Přidání vlastního příkazu  
 Implementace `IVsTextMarkerClient` rozhraní a poskytování ukazatel z značku zlepšuje chování značky několika způsoby. Nejprve to vám umožní zajistit tipy pro vaše značky a provádět příkazy. Také můžete přijímat oznámení události u jednotlivých značek a vytvářet vlastní Kontextová nabídka přes značky. Použijte následující postup pro přidání vlastního příkazu do místní nabídky značky.  
  
#### <a name="to-add-a-custom-command-to-the-context-menu"></a>Přidání vlastního příkazu do kontextové nabídky  
  
1.  Předtím, než se zobrazí v místní nabídce prostředí volá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetMarkerCommandInfo%2A> metoda a předává je ukazatel na text značky vliv a počet položek příkaz v místní nabídce.  
  
     Patří například specifické zarážek příkazy v místní nabídce **odstranit bod přerušení** prostřednictvím **nové zarážek**, jak je uvedeno v následujícím snímku obrazovky.  
  
     ![Místní nabídka značek](../extensibility/media/vsmarkercontextmenu.gif "vsMarkercontextmenu")  
  
2.  Předejte zpět nějaký text identifikace název vlastního příkazu. Například **odstranit bod přerušení** Pokud prostředí již neposkytuje ho mohou být vlastního příkazu. Také předat zpět jestli příkaz je podporované, k dispozici a povolená nebo přepnutí – vypnuté. Prostředí používá tyto informace pro zobrazení vlastního příkazu v místní nabídce správným způsobem.  
  
3.  K provedení příkazu, volání prostředí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> metodu předáním ukazatele text značky a počet příkaz vybrané v místní nabídce.  
  
     Tyto informace z toto volání použijte k provedení stanoví, ať akce text značky vlastního příkazu.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: implementace chyba značky](../extensibility/how-to-implement-error-markers.md)   
 [Postupy: vytvoření vlastní Text značek](../extensibility/how-to-create-custom-text-markers.md)   
 [Postupy: použití značek textu](../extensibility/how-to-use-text-markers.md)