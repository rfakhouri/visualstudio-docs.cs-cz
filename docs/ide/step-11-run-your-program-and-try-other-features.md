---
title: 'Krok 11: Spuštění programu a vyzkoušení dalších funkcí'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 43cb58c65131b5cc7e01b0f59306761a3b275dc7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925924"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Krok 11: Spuštění programu a vyzkoušení dalších funkcí
Program je dokončen a připraven ke spuštění. Můžete spustit program a nastavit barvu <xref:System.Windows.Forms.PictureBox>pozadí. Chcete-li získat další informace, zkuste program vylepšit změnou barvy formuláře, přizpůsobením tlačítek a zaškrtávacím políčkem a změnou vlastností formuláře.

Pokud si chcete stáhnout dokončenou verzi ukázky, přečtěte si [ukázku kurzu dokončení prohlížeče obrázků](https://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 5.](http://go.microsoft.com/fwlink/?LinkId=205206) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-run-your-program-and-set-the-background-color"></a>Spuštění programu a nastavení barvy pozadí

1. Vyberte **F5**nebo na panelu nabídek vyberte **ladit** > **Spustit ladění**.

2. Než otevřete obrázek, klikněte na tlačítko **nastavit barvu pozadí** . Otevře se dialogové okno **Barva** .

     ![Dialogové okno barvy](../ide/media/express_colordialog.png)
dialogového okna barvy

3. Vyberte barvu pro nastavení barvy pozadí ovládacího prvku PictureBox. Prohlédněte si úzce `backgroundButton_Click()` na metodě, abyste porozuměli tomu, jak to funguje.

    > [!NOTE]
    > Obrázek můžete načíst z Internetu vložením jeho adresy URL do dialogového okna **otevřít soubor** . Zkuste najít obrázek s průhledným pozadím, aby se zobrazila barva pozadí.

4. Klikněte na tlačítko **Vymazat obrázek** , abyste se ujistili, že se vymaže. Pak ukončete program kliknutím na tlačítko **Zavřít** .

## <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí

- Změňte barvu formuláře a tlačítek pomocí vlastnosti **BackColor** .

- Přizpůsobte si tlačítka a zaškrtávací políčko pomocí vlastností **Font** a **ForeColor** .

- Změňte vlastnosti **FormBorderStyle** a **ovládací nabídka** formuláře.

- Použijte vlastnosti **AcceptButton** a **CancelButton** vašeho formuláře, aby se tlačítka automaticky brala, když uživatel zvolí klávesu **ENTER** nebo **ESC** . Nastavit program tak, aby otevřel dialogové okno **otevřít soubor** , když uživatel zvolí **ENTER** a zavřít pole, když uživatel zvolí klávesu **ESC**.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Další informace o programování v aplikaci Visual Studio naleznete v tématu [koncepty programování](https://msdn.microsoft.com/Library/65c12cca-af4f-4017-886e-2dbc00a189d6).

- Další informace o Visual Basic najdete v tématu [vývoj aplikací pomocí Visual Basic](/dotnet/visual-basic/developing-apps/index).

- Další informace o vizuálu C#najdete v tématu [Úvod do C# jazyka a .NET Framework](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework).

- Pokud chcete přejít k dalšímu kurzu, přečtěte si [kurz 2: Vytvoření časovaného matematického](../ide/tutorial-2-create-a-timed-math-quiz.md)kvízu

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 10: Napište kód pro další tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).
