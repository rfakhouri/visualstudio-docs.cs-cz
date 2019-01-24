---
title: Zobrazení využití | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cpuutilization
helpviewer_keywords:
- Concurrency Visualizer, CPU Utilization View
ms.assetid: b4f7ceab-3653-4069-bb74-c309aec62866
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 238d821795aaa4e9ef0ac06e117316450b46fda4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54795829"
---
# <a name="utilization-view"></a>Zobrazení využití
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Zobrazení využití** zobrazí informace o procesoru, GPU a jiné systémové prostředky, které jsou používány aktuální proces. Zobrazuje průměrnou core využití procesu analyzované, nečinného procesu, proces systému a další procesy, které jsou spuštěny v systému v čase. Nezobrazí, které konkrétní core je aktivní v daném okamžiku. Například pokud dvě jádra každý systém plně využívá kapacitu 50 procent za dané časové období, pak toto zobrazení uvádí využívané jednoho logického jádra. Generuje rozdělení doby profilování do segmentů krátkého formátu času zobrazení. Pro každý segment grafu zobrazí průměrný počet vlákna procesu, které jsou spuštěny na logických jader během tohoto intervalu.  
  
 ![Zobrazení využití procesoru](../profiling/media/vsts-ppacpuutil.png "VSTS_PPAcpuUtil")  
  
 Graf zobrazuje čas (na ose x) a průměrnou logických jader, které využívají cílového procesu, proces nečinnosti a systémový proces. (Nečinného procesu se zobrazí nečinných jader. Systémový proces je proces ve Windows, které provádí práci jménem jiných procesů). Zbývající procesy, které jsou spuštěny na systémový účet pro využití jakékoli zbývající jader.  
  
 Počet logických jader je zobrazen na ose y. Windows považuje za současné podpoře multithreadingu v hardwaru logických jader (například technologie Hyper-Threading). Proto systém, který má čtyřjádrový procesor, které podporují dva hardwarových vláken na jádro se zobrazí jako systém osm logické jádro. To platí i pro zobrazení jader. Další informace najdete v tématu [zobrazení jader](../profiling/cores-view.md).  
  
 Graf aktivity GPU zobrazuje počet modulů, DirectX používanou v čase.  Modul je používán, pokud zpracovává paketu DMA.  V grafu nezobrazí konkrétní modul DirectX (například 3D modulu, modul Video a ostatní).  
  
## <a name="purpose"></a>Účel  
 Zobrazení využití jako výchozí bod pro vyšetřování výkonu doporučujeme při použití Vizualizátor souběžnosti. Protože v čase poskytuje přehled o stupeň souběžnosti v aplikaci, můžete použít a rychle identifikovat oblasti, které vyžadují optimalizace výkonu nebo paralelního zpracování.  
  
 Pokud vás zajímá optimalizace výkonu, budete asi zkouší identifikovat chování, která nesplňuje vaše očekávání. Můžete také hledat existence a příčinu oblastí, které mají nízké využití logických jader procesoru. Může také být hledáte vzory využití mezi CPU a GPU.  
  
 Pokud vás zajímá paralelní provádění aplikace, které pravděpodobně hledáte buď oblasti vázané na procesor provádění nebo oblasti, ve kterém se využitím procesoru.  
  
 Oblasti vázané na procesor, jsou zelená. Graf zobrazuje jedno jádro využívané, pokud je aplikace sériového portu.  
  
 Oblasti, ve kterém se využitím procesoru jsou šedé. To může představovat body, na kterých je aplikace nečinnosti nebo provádí blokování vstupně-výstupních operací, které poskytují možnosti pro paralelismus podle překrývající se v další práci vázané na procesor.  
  
 Zjistíte chování, které vás zajímají, si můžete přiblížit v dané oblasti tak, že ho vyberete. Po přiblížíte, můžete přepnout na zobrazení vláken nebo zobrazení jader pro podrobnější analýzu.  
  
 Pokud používáte GPU s použitím jazyka C++ AMP nebo DirectX, může zajímat identifikační číslo modulů GPU v použití nebo oblastech, kde je neočekávaně nečinnosti GPU.  
  
## <a name="zooming"></a>Změna měřítka zobrazení  
 Přiblížit na graf využití procesoru nebo graf aktivity GPU, vyberte oddíl nebo použijte nástroj posuvník přiblížení nad grafem. Nastavení přiblížení či oddálení přetrvává při přepínání s dalšími zobrazeními. Znovu zmenšíte pomocí nástroje jezdce přiblížení. Můžete také přiblížit, oddálit stisknutím klávesy Ctrl a posouvání.  
  
## <a name="see-also"></a>Viz také  
 [Vizualizátor souběžnosti](../profiling/concurrency-visualizer.md)   
 [Zobrazení jader](../profiling/cores-view.md)
