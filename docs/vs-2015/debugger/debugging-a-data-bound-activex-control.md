---
title: Ladění ovládacího prvku ActiveX vázaného na Data | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 45a2f6e022c753b0fe543f2265c7ac1961fd474a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752920"
---
# <a name="debugging-a-data-bound-activex-control"></a>Ladění ovládacího prvku ActiveX vázaného na data
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud vyvíjíte ovládacího prvku ActiveX, který bude vázán k ovládacímu prvku zdroje dat, můžete vytvořit svou vlastní aplikaci typu kontejner a použít tento kontejner Chcete-li ladit ovládací prvek ActiveX.  
  
 Můžete například vytvoření aplikace založené na dialogu MFC a umístit ovládací prvek vázaný na data a ovládací prvek zdroje dat v dialogovém okně. Tato aplikace knihovny MFC můžete použít pro testování za běhu a jako kontejner spustitelný pro ladění vašeho ovládacího prvku ActiveX vázaného na data.  
  
## <a name="using-the-test-container"></a>Pomocí testovacího kontejneru  
 Pokud chcete kontejner, který můžete snadno upravit pro podporu různých rozhraní buď ovládacího prvku nebo kontejneru, použijte kontejner testu ActiveX jako spustitelný soubor pro relaci ladění. V kontejneru testů ActiveX, klikněte na tlačítko **možnosti** z **kontejneru** nabídka umožňující různá rozhraní. Další informace najdete v tématu [testování vlastností a událostí pomocí testovacího kontejneru](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917).  
  
 Pokud je potřeba při ladění s vnořením do kontejneru kódu, použijte ladicí verze vašeho kontejneru nebo použijte ladicí verze v kontejneru testů ActiveX. Další informace najdete v tématu [lze kontejner TSTCON vzorku: Kontejner testů ovládacích prvků ActiveX](http://msdn.microsoft.com/72fa40ef-27d3-400c-813f-10b03236e600).  
  
## <a name="see-also"></a>Viz také  
 [COM a ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [ActiveX – ovládací prvky](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)
