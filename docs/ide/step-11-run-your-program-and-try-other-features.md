---
title: 'Krok 11: Spusťte svůj Program a vyzkoušejte jiné funkce'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: efcf0a09b8d148aa6e904eab57f509585b89f5ba
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Krok 11: Spusťte svůj Program a vyzkoušejte jiné funkce
Váš program je připraven ke spuštění a dokončení. Můžete spustit program a nastavení barvy pozadí PictureBox. Další informace, pokuste se program zlepšit Změna barvy formuláře, přizpůsobení tlačítka a zaškrtávací políčko a změna vlastností formuláře.  

 Si můžete stáhnout dokončené verzi příkladu [kurz ukázka dokončení Prohlížeč obrázků](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  

### <a name="to-run-your-program-and-set-the-background-color"></a>Chcete-li spustit program a nastavení barvy pozadí  

1.  Zvolte F5, nebo v řádku nabídek zvolte **ladění**, **spustit ladění**.  

2.  Před otevřením obrázku, vyberte **nastavení barvy pozadí** tlačítko. **Barva** otevře se dialogové okno.  

     ![Dialogové okno barvy](../ide/media/express_colordialog.png "Express_ColorDialog")  
Dialogové okno barvy  

3.  Vyberte barvu, která má nastavení barvy pozadí PictureBox. Prohlédněte si blíže `backgroundButton_Click()` metoda pochopit, jak to funguje.  

    > [!NOTE]
    >  Můžete načíst obrázek z Internetu vložením jeho URL do **otevření souboru** dialogové okno. Zkuste najít bitovou kopii s průhledným pozadím, takže zobrazí barva pozadí.  

4.  Vyberte **Vymazat obrázek** tlačítko zajistěte, aby se vymaže. Ukončete program a vybrat **Zavřít** tlačítko.  

### <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí  

-   Změnit barvu formulář a tlačítka, pomocí **BackColor** vlastnost.  

-   Přizpůsobte si tlačítka a zaškrtávací políčko pomocí **písma** a **ForeColor** vlastnosti.  

-   Změnu svého formuláře **FormBorderStyle** a **místní nabídka** vlastnosti.  

-   Pomocí svého formuláře **AcceptButton** a **CancelButton** vlastnosti tak, že tlačítka jsou automaticky vybrali, když uživatel vybere klávesu ENTER nebo ESC. Ujistěte se, program otevřete **otevřít soubor** dialogové okno když uživatel vybere zadejte a zavřít okno, když uživatel vybere ESC.  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Další informace o programování v sadě Visual Studio, najdete v části [koncepty programování](http://msdn.microsoft.com/Library/65c12cca-af4f-4017-886e-2dbc00a189d6).  

-   Další informace o jazyka Visual Basic, najdete v části [vývoj aplikací v jazyce Visual Basic](/dotnet/visual-basic/developing-apps/index).  

-   Další informace o Visual C#, najdete v části [Úvod do jazyka C# a rozhraní .NET Framework](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework).  

-   Pokud chcete přejít na další kurzu, přečtěte si téma [kurzu 2: vytvoření vypršel časový limit matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 10: psát kód pro přídavná tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).
