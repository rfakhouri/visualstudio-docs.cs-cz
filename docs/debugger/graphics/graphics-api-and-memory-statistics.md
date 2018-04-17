---
title: Grafické rozhraní API a statistiky paměti | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.apistatistics
- vs.graphics.memorystatistics
ms.assetid: 27d2f303-e3ed-4219-9009-345a0d849506
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b57edb59984537638dd32b621406775087ba680e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="graphics-api-and-memory-statistics"></a>Grafické rozhraní API a statistiky paměti
<!-- VERSIONLESS -->
Visual Studio 2017 a větší podporu statistiku grafické rozhraní API a nástroje statistiky paměti.  Tyto dva nástroje umožňují zobrazit různé bity informace na využití Direct3D rozhraní API a také využití paměti grafického procesoru různých prostředků.

## <a name="graphics-api-statistics"></a>Grafické rozhraní API statistiky
Statistické údaje grafické rozhraní API v diagnostiky grafiky Visual Studio umožňuje zobrazit všechny Direct3D – volání, které byly provedeny a počet jednotlivých volání.  Chcete-li zobrazit okno, vyberte **zobrazení > statistiky rozhraní API** položku nabídky.

![Rozhraní API statistiky](media/gfx_diag_api_statistics.png)

Tento nástroj může být užitečný v zjišťování, že rozhraní DirectX volání že nemusí zjistíte, které provádíme za nebo volání, které provádíte příliš často.

V okně pro kopírování všechna data kliknete pravým tlačítkem jako sdílený svazek clusteru, který lze vložit do něco podobného jako aplikace Excel k další analýze.

## <a name="memory-statistics"></a>Statistiky paměti
Tento nástroj se zobrazí, kolik paměti je ovladač grafiky přidělování pro prostředky vytvoříte v rámečku.  Chcete-li zobrazit toto okno, vyberte **zobrazení > paměti statistiky** položku nabídky.

![Statistiky paměti](media/gfx_diag_memory_statistics.png)

**GPU přidělení** sloupec zobrazuje velikost paměti, které zobrazí v události **událostí** sloupce.  Můžete také vybrat ikona sledování ![ikona sledování](media/gfx_watch.png) zobrazíte [historie prostředků](graphics-event-list.md#resource-history) pro zvolenou událost.

Stejně jako u rozhraní API statistiky nástroj, kliknete pravým tlačítkem v okně pro kopírování všechna data jako sdílený svazek clusteru, který lze vložit do něco podobného jako aplikace Excel k další analýze.

## <a name="see-also"></a>Viz také  
[Diagnostika grafiky (ladění grafiky DirectX)](visual-studio-graphics-diagnostics.md)   
[Historie prostředků](graphics-event-list.md#resource-history)
<!-- /VERSIONLESS -->