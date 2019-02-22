---
title: 'Postupy: Změnit počítač pro přehrávání diagnostiky grafiky | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b9aa3ea-29a0-4e21-bc57-936f33537b5c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0af2fc0c847c88aa4cc7cb0b15a80e9bdfa4703d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723341"
---
# <a name="how-to-change-the-graphics-diagnostics-playback-machine"></a>Postupy: Změnit počítač pro přehrávání diagnostiky grafiky
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
- [Dokument grafických protokolů](graphics-log-document.md)