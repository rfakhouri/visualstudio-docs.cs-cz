---
title: Grafické rozhraní API a Statistika paměti | Dokumentace Microsoftu
ms.date: 03/02/2017
ms.topic: conceptual
f1_keywords:
- vs.graphics.apistatistics
- vs.graphics.memorystatistics
ms.assetid: 27d2f303-e3ed-4219-9009-345a0d849506
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7810889d4af411477573c71aa694d797a90763f3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720598"
---
# <a name="graphics-api-and-memory-statistics"></a>Grafické rozhraní API a Statistika paměti
<!-- VERSIONLESS --> Visual Studio 2017 nebo novější podporují nástroje statistiky grafické rozhraní API a Statistika paměti.  Tyto dva nástroje umožňují zobrazit různé části informace o použití rozhraní API Direct3D, jakož i spotřebu paměti GPU z různých zdrojů.

## <a name="graphics-api-statistics"></a>Statistika API grafiky
Statistika API grafiky v Diagnostika grafiky sady Visual Studio umožňuje zobrazit všechna volání rozhraní Direct3D, které byly provedeny a počet každé volání.  Chcete-li zobrazit okno, vyberte **zobrazení > Statistika API** položky nabídky.

![Statistika API](media/gfx_diag_api_statistics.png)

Tento nástroj může být užitečná v zjišťují, že volání rozhraní DirectX, že nemusí zjistíte, které vytváříte, nebo volání, které provádíte příliš často.

V okně všechny kopie dat kliknete pravým tlačítkem jako sdílený svazek clusteru, který může vložit na něco, jako je Excel k další analýze.

## <a name="memory-statistics"></a>Statistika paměti
Tento nástroj se zobrazí, kolik paměti je ovladač grafiky přidělování prostředků vytvoříte v objektu frame.  Chcete-li zobrazit toto okno, vyberte **zobrazení > Statistika paměti** položky nabídky.

![Statistika paměti](media/gfx_diag_memory_statistics.png)

**Přidělení GPU** sloupec zobrazuje množství paměti používané události zobrazí v **události** sloupce.  Můžete také vybrat ikonu watch ![ikona sledování](media/gfx_watch.png) zobrazíte [rie prostředku](graphics-event-list.md#resource-history) pro zvolenou událost.

Stejně jako u nástroj Statistika API kliknete pravým tlačítkem v okně všechny kopie dat jako sdílený svazek clusteru, který může vložit na něco, jako je Excel k další analýze.

## <a name="see-also"></a>Viz také
- [Diagnostika grafiky (ladění grafiky DirectX)](visual-studio-graphics-diagnostics.md)
- [Historie prostředku](graphics-event-list.md#resource-history)
<!-- /VERSIONLESS -->