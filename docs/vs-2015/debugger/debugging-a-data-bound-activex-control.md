---
title: Ladění ovládacího prvku ActiveX vázaného na Data | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6642b3687e4459cc001aef14ce0c1186231f8c97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674189"
---
# <a name="debugging-a-data-bound-activex-control"></a>Ladění ovládacího prvku ActiveX vázaného na data
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ladění ovládacího prvku ActiveX vázaného](https://docs.microsoft.com/visualstudio/debugger/debugging-a-data-bound-activex-control).  
  
Pokud vyvíjíte ovládacího prvku ActiveX, který bude vázán k ovládacímu prvku zdroje dat, můžete vytvořit svou vlastní aplikaci typu kontejner a použít tento kontejner Chcete-li ladit ovládací prvek ActiveX.  
  
 Můžete například vytvoření aplikace založené na dialogu MFC a umístit ovládací prvek vázaný na data a ovládací prvek zdroje dat v dialogovém okně. Tato aplikace knihovny MFC můžete použít pro testování za běhu a jako kontejner spustitelný pro ladění vašeho ovládacího prvku ActiveX vázaného na data.  
  
## <a name="using-the-test-container"></a>Pomocí testovacího kontejneru  
 Pokud chcete kontejner, který můžete snadno upravit pro podporu různých rozhraní buď ovládacího prvku nebo kontejneru, použijte kontejner testu ActiveX jako spustitelný soubor pro relaci ladění. V kontejneru testů ActiveX, klikněte na tlačítko **možnosti** z **kontejneru** nabídka umožňující různá rozhraní. Další informace najdete v tématu [testování vlastností a událostí pomocí testovacího kontejneru](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917).  
  
 Pokud je potřeba při ladění s vnořením do kontejneru kódu, použijte ladicí verze vašeho kontejneru nebo použijte ladicí verze v kontejneru testů ActiveX. Další informace najdete v tématu [lze kontejner TSTCON vzorku: kontejner testů ovládacích prvků ActiveX](http://msdn.microsoft.com/en-us/72fa40ef-27d3-400c-813f-10b03236e600).  
  
## <a name="see-also"></a>Viz také  
 [COM a ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [ActiveX – ovládací prvky](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)



