---
title: 'Postupy: Změna počítače pro přehrávání diagnostiky grafiky | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b9aa3ea-29a0-4e21-bc57-936f33537b5c
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e33d2acc46cbf92c9b2bbd699903ad3169661a54
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668464"
---
# <a name="how-to-change-the-graphics-diagnostics-playback-machine"></a>Postupy: Změna počítače pro přehrávání diagnostiky grafiky
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: Změna počítače pro přehrávání diagnostiky grafiky](https://docs.microsoft.com/visualstudio/debugger/graphics/how-to-change-the-graphics-diagnostics-playback-machine).  
  
Můžete přehrávat grafické informace pomocí místního počítače nebo vzdáleném počítači či zařízení.  
  
## <a name="choosing-a-playback-machine"></a>Volba počítače pro přehrávání  
 Počítač pro přehrávání je počítač nebo zařízení, které slouží k přehrání událostí grafiky z grafického protokolu. Obvykle místní počítač je nejpohodlnější možnost, ale problém vykreslování se nemusí reprodukovat na počítači, který má jiný hardware nebo verze ovladače než počítač, kde byl zachycen; Pokud k tomu dojde, můžete zvolit vzdálený počítač pro přehrávání, který lépe reprodukuje problém a nadále používat svůj vývojářský počítač k její diagnostice.  
  
#### <a name="to-use-the-local-machine-to-play-back-graphics-information"></a>Použití místního počítače k přehrání grafické informace  
  
1.  V okně dokumentu protokol grafiky zvolte **počítač pro přehrávání** odkaz. **Připojení pro vzdálený ladicí program** zobrazí se dialogové okno.  
  
2.  V části **ruční konfigurace**v **adresu** vlastnost, zadejte `localhost`.  
  
3.  Nastavte **režim ověřování** vlastnost **žádný**.  
  
4.  Zvolte **vyberte** tlačítko.  
  
#### <a name="to-use-a-remote-machine-to-play-back-graphics-information"></a>Použití vzdáleného počítače k přehrání grafické informace  
  
1.  V okně dokumentu protokol grafiky zvolte **počítač pro přehrávání** odkaz. **Připojení pro vzdálený ladicí program** zobrazí se dialogové okno.  
  
2.  V části **ruční konfigurace**v **adresu** vlastnost, zadejte název domény Windows nebo IP adresu počítače nebo zařízení, které chcete použít k přehrání grafické informace.  
  
3.  Zadejte typ ověřování, který chcete použít k zabezpečení připojení k počítači pro přehrávání.  
  
    -   Ověřování Windows, nastavte **režim ověřování** vlastnost **Windows**.  
  
    -   Bez ověřování, nastavte **režim ověřování** vlastnost **žádný**.  
  
4.  Zvolte **vyberte** tlačítko.  
  
> [!NOTE]
>  **Připojení pro vzdálený ladicí program** dialogové okno může také zobrazit cíle vzdáleného ladění, které jsou připojeny přímo do svého vývojového počítače nebo jsou ve stejné podsíti. Jeden z těchto vzdálených cílů ladění můžete použít jako stroj přehrávání diagnostiky grafiky bez ruční konfigurace. V **připojení pro vzdálený ladicí program** dialogového okna, vyberte cíl, má a klikněte na tlačítko **vyberte** tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Dokument grafických protokolů](../debugger/graphics-log-document.md)



