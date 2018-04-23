---
title: 'Postupy: Vytvoření základní textury'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0222e8bf-d29f-421b-9b1f-123d500fa179
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45bb45c12e7cbdbec37574f371daf4cd6c207fb1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-texture"></a>Postupy: Vytvoření základní textury
Tento dokument ukazuje, jak vytvořit základní texture pomocí editoru obrázků.

 Tento dokument ukazuje tyto aktivity:

-   Nastavení velikosti pole textury

-   Nastavení barvy popředí a na pozadí

-   Použitím kanálu alfa (průhlednost)

-   Pomocí **vyplnění** a **elipsy** nástroje

-   Nastavení vlastnosti nástroje

## <a name="creating-a-basic-texture"></a>Vytvoření základní textury
 Editor obrázků slouží k vytvoření a úpravám bitové kopie a textury pro hry nebo aplikace.

 Následující kroky ukazují, jak vytvořit texture, který představuje cíl "terč". Po dokončení textury by měla vypadat jako na následujícím obrázku. K předvedení lépe průhlednost v textury, Editor obrázků má nakonfigurované použití vzoru zelený, šachovnicová mřížka můžete ho zobrazit.

 !["Terč" cíl s průhlednost zobrazené zeleně](../designers/media/digit-bullseye-texture-in-editor.png "číslice-terč-Texture-v-editoru")

 Než začnete, ujistěte se, že **vlastnosti** zobrazí se okno. Můžete použít **vlastnosti** okna nastavit velikost bitové kopie, změňte vlastnosti nástroje a zadat barvy při práci.

#### <a name="to-create-a-bullseye-target-texture"></a>Chcete-li vytvořit cíl texturou "terč"

1.  Vytvořte texture pro práci s. Informace o tom, jak do projektu přidejte texturou, najdete v části Začínáme v [Editor obrázků](../designers/image-editor.md).

2.  Nastavte velikost bitové kopie na 512 x 512 pixelů. V **vlastnosti** nastavte hodnoty **šířka** a **výška** vlastnosti, které chcete `512`.

3.  Na panelu nástrojů editoru obrázků, vyberte **vyplnění** nástroj. **Vlastnosti** okno teď zobrazuje vlastnosti **vyplnění** spolu s vlastnosti bitové kopie.

4.  Nastavte barvu popředí na černé zcela průhledná. V **vlastnosti** okno v **barvy** vlastnosti skupiny, vyberte **popředí**. Nastavte hodnoty **R**, **G**, **B**, a **A** vlastnosti vedle volby barev k `0`.

5.  Na panelu nástrojů editoru obrázků, vyberte **vyplnění** nástroje a stiskněte a podržte klávesu Shift a zvolit jakýkoli bod v bitové kopii. Pomocí klávesy Shift způsobí, že alfa hodnotu barvu výplně nahradit barvu v obrázku; alfa hodnotu, jinak se používá a přizpůsobte barvu výplně společně s barvu v obrázku.

    > [!IMPORTANT]
    >  Tento krok, společně s výběr barev v předchozím kroku, zajistí, že základní bitová kopie je připravená pro cíl texture "terč", který bude kreslení. Když je obrázek vyplněn transparentní černé – a protože ohraničení cíl je černá – budou existovat žádné aliasy artefakty kolem cíl.

6.  Na panelu nástrojů editoru obrázků, vyberte **elipsy** nástroj.

7.  Nastavte na černé plně neprůhledné barvu popředí. Nastavte hodnoty **R**, **G**, a **B** vlastnosti, které chcete `0` a hodnota **A** vlastnost `255`.

8.  Nastaví barvu pozadí na bílou plně neprůhledné. V **vlastnosti** okno v **barvy** vlastnosti skupiny, vyberte **pozadí**. Nastavte hodnoty **R**, **G**, **B**, a **A** vlastnosti, které chcete `255`.

9. Nastavená šířka obrysu se třemi tečkami. V **vlastnosti** okno v **vzhled** vlastnosti skupiny, nastavte hodnotu **šířka** vlastnost `8`.

10. Ujistěte se, že je povolená vyhlazení. V **vlastnosti** okno v **vzhled** vlastnosti skupiny, ujistěte se, že **vyhlazení** je nastavena.

11. Pomocí **elipsy** nástroj, kreslení kruh z pixelů souřadnice `(3, 3)` na pixel souřadnice `(508, 508)`. Kreslení na kruh další snadno můžete stiskněte a podržte klávesu Shift při kreslení.

    > [!NOTE]
    >  Souřadnice pixelů aktuální umístění ukazatele jsou zobrazené na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] stavový řádek.

12. Změňte barvu pozadí. Nastavit **R** k `44`, **G** k `165`, **B** k `211`, a **A** k `255`.

13. Kreslení jiné kruh z pixelů souřadnice `(64, 64)` na pixel souřadnice `(448, 448)`.

14. Změníte barvu pozadí zpět na plně neprůhledné prázdné. Nastavit **R**, **G**, **B**, a **A** k `255`.

15. Kreslení jiné kruh z pixelů souřadnice `(128, 128)` na pixel souřadnice `(384, 384)`.

16. Změňte barvu pozadí. Nastavit **R** k `255`, **G** a **B** k `64`, a **A** k `255`.

17. Kreslení jiné kruh z pixelů souřadnice `(192, 192)` na pixel souřadnice `(320, 320)`.

 Texture cíl "terč" bylo dokončeno. Zde je výsledný obraz, zobrazí s průhlednost.

 ![Dokončení "terč" cíle texture](../designers/media/gfx_image_demo_bullseye.png "gfx_image_demo_bullseye")

 Jako další krok můžete vygenerovat MIP úrovně pro tento texture. Informace najdete v tématu [postupy: vytvoření a upravit MIP úrovně](../designers/how-to-create-and-modify-mip-levels.md).

## <a name="see-also"></a>Viz také

- [Editor obrázků](../designers/image-editor.md)