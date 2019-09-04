---
title: 'Krok 11: Spuštění programu a vyzkoušení dalších funkcí'
ms.date: 08/30/2019
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.devlang:
- csharp
- vb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5486aa4d2effa3feb03b31bace7a9cfc86fd9925
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293598"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Krok 11: Spuštění programu a vyzkoušení dalších funkcí

Program je dokončen a připraven ke spuštění. Můžete spustit program a nastavit barvu <xref:System.Windows.Forms.PictureBox>pozadí. Chcete-li získat další informace, zkuste program vylepšit změnou barvy formuláře, přizpůsobením tlačítek a zaškrtávacím políčkem a změnou vlastností formuláře.

## <a name="how-to-run-your-program-and-set-the-background-color"></a>Jak spustit program a nastavit barvu pozadí

1. Vyberte **F5**nebo na panelu nabídek vyberte **ladit** > **Spustit ladění**.

1. Než otevřete obrázek, klikněte na tlačítko **nastavit barvu pozadí** . Otevře se dialogové okno **Barva** .

     ![Dialogové okno barvy](../ide/media/express_colordialog.png)<br/>
***Barva*** *dialogové okno*

1. Vyberte barvu pro nastavení barvy pozadí ovládacího prvku PictureBox. Prohlédněte si úzce `backgroundButton_Click()` na metodě ( `BackgroundButton_Click()`nebo), abyste pochopili, jak funguje.

    > [!NOTE]
    > Obrázek můžete načíst z Internetu vložením jeho adresy URL do dialogového okna **otevřít soubor** . Zkuste najít obrázek s průhledným pozadím, aby se zobrazila barva pozadí.

1. Klikněte na tlačítko **Vymazat obrázek** , abyste se ujistili, že se vymaže. Pak ukončete program kliknutím na tlačítko **Zavřít** .

## <a name="try-other-features"></a>Vyzkoušení dalších funkcí

* Změňte barvu formuláře a tlačítek pomocí vlastnosti **BackColor** .

* Přizpůsobte si tlačítka a zaškrtávací políčko pomocí vlastností **Font** a **ForeColor** .

* Změňte vlastnosti **FormBorderStyle** a **ovládací nabídka** formuláře.

* Použijte vlastnosti **AcceptButton** a **CancelButton** vašeho formuláře, aby se tlačítka automaticky brala, když uživatel zvolí klávesu **ENTER** nebo **ESC** . Nastavit program tak, aby otevřel dialogové okno **otevřít soubor** , když uživatel zvolí **ENTER** a zavřít pole, když uživatel zvolí **klávesu ESC**.

## <a name="next-steps"></a>Další postup

Další informace najdete v následujícím kurzu:

> [!div class="nextstepaction"]
> [Kurz 2: Vytvoření časovaného matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md)

Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 10: Napište kód pro další tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).

## <a name="see-also"></a>Viz také:

* [Další C# kurzy](/visualstudio/get-started/csharp/)
* [Další kurzy Visual Basic](/visualstudio/get-started/visual-basic/)
* [C++návodu](../ide/getting-started-with-cpp-in-visual-studio.md)
