---
title: Ladění ovládacího prvku ActiveX vázané na Data | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df11571bb1e37d458fd647ce1524f67432617b8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474288"
---
# <a name="debugging-a-data-bound-activex-control"></a>Ladění ovládacího prvku ActiveX vázaného na data
Pokud vyvíjíte ovládací prvek ActiveX, který bude vázán k prvku zdroje dat, můžete vytvořit vlastní aplikaci kontejneru a použití tohoto kontejneru k ladění ovládacího prvku ActiveX.  
  
 Můžete například vytvořit v aplikaci na základě dialogové okno knihovny MFC a umístěte a vázané na data ovládacího prvku zdroje dat v dialogovém okně. Tuto aplikaci MFC můžete používat pro testování spuštění a jako kontejneru spustitelný soubor pro ladění ovládacího prvku ActiveX vázané na data.  
  
## <a name="using-the-test-container"></a>Pomocí testovacího kontejneru  
 Pokud chcete do kontejneru, který můžete snadno upravit pro podporu různých rozhraní na buď ovládací prvek nebo kontejner, použijte kontejner testů ActiveX jako spustitelný soubor pro relaci ladění. V kontejneru ActiveX testu, klikněte na tlačítko **možnosti** z **kontejneru** chcete povolit různé rozhraní, v nabídce. Další informace najdete v tématu [testování vlastností a událostí pomocí testovacího kontejneru](/cpp/mfc/testing-properties-and-events-with-test-container).  
  
 Pokud potřebujete kroku do kódu kontejneru při ladění, použijte ladicí verze vašeho kontejneru nebo použijte ladicí verze Test kontejneru ActiveX. Další informace najdete v tématu [TSTCON ukázka: kontejner testů ovládacích prvků ActiveX](http://msdn.microsoft.com/en-us/72fa40ef-27d3-400c-813f-10b03236e600).  
  
## <a name="see-also"></a>Viz také  
 [COM a prvků ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [ActiveX – ovládací prvky](/cpp/mfc/activex-controls)