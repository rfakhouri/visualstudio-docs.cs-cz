---
title: Zobrazení využití | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cpuutilization
helpviewer_keywords:
- Concurrency Visualizer, CPU Utilization View
ms.assetid: b4f7ceab-3653-4069-bb74-c309aec62866
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 835226dc867f290c3cd3f553895687abdb895207
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477103"
---
# <a name="utilization-view"></a>Zobrazení využití
**Zobrazení využití** zobrazí informace o procesoru, GPU a jiné systémové prostředky, které jsou používány aktuální proces (zvolte **analyzovat** > **souběžnosti Vizualizér** zahájíte vizualizér souběžnosti). Zobrazuje průměrnou základní využití procesu analyzovaných, nečinného procesu, proces systému a další procesy, které běží na serveru v čase. Nezobrazí, které konkrétní základní je aktivní v daném okamžiku. Například pokud každé dvě jádra jsou spuštěné v 50 procent kapacity pro dané časové období, pak toto zobrazení uvádí jednoho logického jádra využívání. Zobrazení je generován dělení profilování čas na krátkou dobu segmenty. Pro každý segment graf ukazuje zeměpisný průměrný počet vláken procesů, které jsou prováděny logické jader na během tohoto intervalu.  
  
 ![Zobrazení využití procesoru](../profiling/media/vsts_ppacpuutil.png "VSTS_PPAcpuUtil")  
  
 Graf zobrazuje čas (na ose x) a průměrnou logické jader, které se používají ve tento cílový proces, nečinného procesu a procesu systému. (Nečinného procesu ukazuje nečinných jader. Proces systému je proces v systému Windows, která může provádět pracovní jménem jiných procesů). Zbývající procesy, které jsou spuštěny na systémový účet pro využití všechny zbývající jader.  
  
 Počet jader logické se zobrazí na ose y. Windows zpracovává souběžných podpora více vláken v hardwaru jako logická jádra (například technologie Hyper-Threading). Systém, který má čtyřjádrový procesor, který je podpora dvěma vlákny hardwaru na základní se proto zobrazí jako systém osm logické procesory. To platí také pro zobrazení jader. Další informace najdete v tématu [zobrazení jader](../profiling/cores-view.md).  
  
 Aktivita GPU graf znázorňuje počet modulů, DirectX používán v čase.  Modul je používán, pokud se zpracovává paket přímý přístup do paměti.  Graf nezobrazí konkrétní modul DirectX (například 3D modul, modul videa a jiné).  
  
## <a name="purpose"></a>Účel  
 Zobrazení využití doporučujeme jako výchozí bod pro vyšetřování výkon při použití vizualizér souběžnosti. Protože poskytuje přehled stupeň souběžnosti v aplikaci v čase, můžete ji rychle identifikovat oblasti, které vyžadují optimalizace výkonu nebo paralelizace.  
  
 Pokud vás zajímá optimalizace výkonu, může se pokoušíte určit chování, které nevyhovuje vašim požadavkům. Můžete také hledat existence a příčina oblastí, které mají nízké využití logické jader procesoru. Také může vyhledávání vzorů využití mezi procesoru a GPU.  
  
 Pokud vás zajímá paralelním prováděním aplikace, se pravděpodobně buď vázané na procesor oblasti provádění nebo oblasti, kde nejsou využitím procesoru.  
  
 Zelená jsou vázané na procesor oblasti. Graf zobrazuje jednoho jádra využívání, pokud je aplikace sériového portu.  
  
 Oblasti, kde nejsou využitím procesoru jsou šedé. To může představovat body, na kterých je aplikace nečinnosti nebo provádění blokování vstupně-výstupní operace zadejte příležitosti pro paralelismus překrývající se s jinou práci vázané na procesor.  
  
 Po nalezení chování týkající se můžete přiblížit na danou oblast výběrem. Po zvětšení, můžete přepnout na zobrazení vláken nebo zobrazení jader pro více podrobné analýzy.  
  
 Pokud používáte GPU pomocí C++ AMP nebo DirectX, může zajímat identifikace počet modulů GPU v použití nebo oblastech, kde je GPU neočekávaně nečinnosti.  
  
## <a name="zoom"></a>Lupa  
 Chcete-li zvětšit graf využití procesoru nebo graf aktivity GPU, vyberte oddíl nebo nástroj posuvníku přiblížení výše grafu. Nastavení přiblížení či oddálení trvá jako přepínače s dalšími zobrazeními. Chcete-li znovu oddálení použijte nástroj přiblížení posuvníku. Také můžete zvětšit pomocí kombinace kláves Ctrl + scroll.  
  
## <a name="see-also"></a>Viz také:  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení jader](../profiling/cores-view.md)