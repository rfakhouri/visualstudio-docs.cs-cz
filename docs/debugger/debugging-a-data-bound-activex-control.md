---
title: Ladění ovládacího prvku ActiveX vázaného na Data | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5b3d5a58c87988c950328a8b0136986b3a149f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62852427"
---
# <a name="debugging-a-data-bound-activex-control"></a>Ladění ovládacího prvku ActiveX vázaného na data
Pokud vyvíjíte ovládacího prvku ActiveX, který bude vázán k ovládacímu prvku zdroje dat, můžete vytvořit svou vlastní aplikaci typu kontejner a použít tento kontejner Chcete-li ladit ovládací prvek ActiveX.

 Můžete například vytvoření aplikace založené na dialogu MFC a umístit ovládací prvek vázaný na data a ovládací prvek zdroje dat v dialogovém okně. Tato aplikace knihovny MFC můžete použít pro testování za běhu a jako kontejner spustitelný pro ladění vašeho ovládacího prvku ActiveX vázaného na data.

## <a name="using-the-test-container"></a>Pomocí testovacího kontejneru
 Pokud chcete kontejner, který můžete snadno upravit pro podporu různých rozhraní buď ovládacího prvku nebo kontejneru, použijte kontejner testu ActiveX jako spustitelný soubor pro relaci ladění. V kontejneru testů ActiveX, klikněte na tlačítko **možnosti** z **kontejneru** nabídka umožňující různá rozhraní. Další informace najdete v tématu [testování vlastností a událostí pomocí testovacího kontejneru](/cpp/mfc/testing-properties-and-events-with-test-container).

 Pokud je potřeba při ladění s vnořením do kontejneru kódu, použijte ladicí verze vašeho kontejneru nebo použijte ladicí verze v kontejneru testů ActiveX. Další informace najdete v tématu [lze kontejner TSTCON vzorku: Kontejner testů ovládacích prvků ActiveX](https://msdn.microsoft.com/library/72fa40ef-27d3-400c-813f-10b03236e600).

## <a name="see-also"></a>Viz také
- [Ladění modelů COM a prvků ActiveX](../debugger/com-and-activex-debugging.md)
- [ActiveX – ovládací prvky](/cpp/mfc/activex-controls)