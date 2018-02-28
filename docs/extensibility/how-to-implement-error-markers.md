---
title: "Postupy: implementace značek chyba | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - error markers
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d41c1bf063ea074df217934a00f73291a10e051d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-error-markers"></a>Postupy: implementace chyba značky
Chyba značky (nebo červené podtržení vlnovkou) jsou nejobtížnější přizpůsobení textového editoru k implementaci. Ale výhody, které uvedou uživatelům vaší VSPackage můžete daleko převáží nad náklady na umožníte jim. Chyba značky trochu označte text, který vaše analyzátoru jazyka považuje za nesprávné vlnovkou nebo vlnovkami red řádek. Tento ukazatel pomůže vizuálně zobrazením nesprávný kód programátory v jazyce.  
  
 Implementace červené podtržení vlnovkou pomocí značek text. Platí jazyka služby přidat červené podtržení vlnovkou na textová vyrovnávací paměť jako pozadí průchodu, v době nečinnosti nebo ve vláknu na pozadí.  
  
### <a name="to-implement-the-red-wavy-underline-feature"></a>K implementaci funkci red podtržení vlnovkou  
  
1.  Vyberte text, pod kterým chcete umístit red vlnovkou.  
  
2.  Vytvořit značku typu `MARKER_CODESENSE_ERROR`. Další informace najdete v tématu [postupy: Přidání značek standardní Text](../extensibility/how-to-add-standard-text-markers.md).  
  
3.  Poté předat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> ukazatel rozhraní.  
  
 Tento proces také vám umožní vytvořit tip text nebo speciální Kontextová nabídka přes danou značku. Další informace najdete v tématu [postupy: Přidání značek standardní Text](../extensibility/how-to-add-standard-text-markers.md).  
  
 Následující objekty jsou požadovány, než lze zobrazit chyba značky.  
  
-   Analyzátor.  
  
-   Úloha zprostředkovatele (tedy implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>) který udržuje záznam změn v řádku informace za účelem zjištění řádky, které chcete být znovu Analyzovaná.  
  
-   Filtr zobrazení textu, který zachycuje vsuvka události změn pomocí zobrazení <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>) metoda.  
  
 Analyzátor, úloha zprostředkovatele a Filtr zadejte infrastruktury potřebné k ověření, chyba značky. Následující kroky obsahují proces pro zobrazení značek chyby.  
  
1.  V zobrazení, které je filtrované získá filtr ukazatel na úloh zprostředkovatele spojeného s daty tohoto zobrazení.  
  
    > [!NOTE]
    >  Můžete použít stejný příkaz Filtr metoda tipy, dokončování, chyba značky a tak dále.  
  
2.  Když filtr obdrží událost označující, že byl přesunut do jiného řádku, vytvoří se úloha ke kontrole chyb.  
  
3.  Obslužná rutina úloh ověří, zda je na řádku nekonzistence. Pokud ano, analyzuje čáry použité k chybám.  
  
4.  Pokud k chybám, zprostředkovatele úloh vytvoří instanci položky úloh. Tato instance vytvoří značky text, který prostředí používá jako značky k chybě v zobrazení textu.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: Přidání značek standardního textu](../extensibility/how-to-add-standard-text-markers.md)   
 [Postupy: vytvoření vlastní Text značek](../extensibility/how-to-create-custom-text-markers.md)   
 [Postupy: použití značek textu](../extensibility/how-to-use-text-markers.md)