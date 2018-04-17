---
title: 'Krok 1: Vytvořte projekt Formulářové aplikace Windows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b455fbbd5474d03e61827cdee74cdd586bc2024b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="step-1-create-a-windows-forms-application-project"></a>Krok 1: Vytvořte projekt formulářové aplikace Windows
Když vytvoříte Prohlížeč obrázků, prvním krokem je vytvoření projektu aplikace Windows Forms.  
  
 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v části [kurzu 1: vytvoření prohlížeče obrázků v jazyce Visual Basic – Video 1](http://go.microsoft.com/fwlink/?LinkId=205209) nebo [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  
  
### <a name="to-create-a-windows-forms-application-project"></a>Vytvoření projektu aplikace Windows Forms  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**. Dialogové okno by měla vypadat takto.  
  
     ![Dialogové okno Nový projekt](../ide/media/newprojectdialogcallouts.png "NewProjectDialogCallouts")  
Dialogové okno Nový projekt  
  
2.  Vyberte buď **Visual C#** nebo **jazyka Visual Basic** v **nainstalovaných šablonách** seznamu.  
  
3.  V seznamu šablon, vyberte **formulářové aplikace Windows** ikonu. Název nového formuláře **PictureViewer**a potom zvolte **OK** tlačítko.  
  
     Visual Studio vytvoří řešení pro váš program. Řešení slouží jako kontejner pro všechny projekty a soubory potřebné podle vašeho programu. Tyto podmínky se vysvětlené podrobněji později v tomto kurzu.  
  
4.  Následující obrázek znázorňuje, co teď byste měli vidět v sadě Visual Studio rozhraní.  
  
    > [!NOTE]
    >  Rozložení okna nemusí přesně vypadat tento obrázek. Rozložení přesné okna závisí na verzi sady Visual Studio, programovací jazyk, který používáte a dalších faktorů. Však ověřte, že všechny tři okna se zobrazí.  
  
     ![Okno IDE](../ide/media/express_ideoverview_visio.png "Express_IDEOverview_Visio")  
Okno IDE  
  
     Rozhraní obsahuje tři windows: hlavní okno **Průzkumníku řešení**a **vlastnosti** okno.  
  
     Pokud některé z těchto windows chybí, proveďte obnovení výchozího rozložení okna, v nabídce panelu Výběr **okno**, **resetovat rozložení okna**. Windows můžete zobrazit také pomocí příkazů nabídky. Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno** nebo **Průzkumníku řešení**. Pokud jiné windows jsou otevřené, zavřete je a vybrat **zavřete** (tlačítko v pravém horním rohu, jejich x).  
  
5.  Na obrázku vidíte následující windows (Změna po směru hodinových ručiček z levého horního rohu):  
  
    -   **Hlavní okno** v tomto okně můžete to udělat většinu práce, například práci s formuláři a úpravy kódu. Na obrázku zobrazí se v formuláře v editoru formuláře. V horní části okna **– úvodní stránka** kartě a **Form1.cs [Design]** zobrazí karta. (V jazyku Visual Basic, karta název končí VB místo. cs.)  
  
    -   **Okno Průzkumníka řešení** v tomto okně můžete zobrazit a přejděte na všechny položky ve vašem řešení. Pokud se rozhodnete soubor obsah **vlastnosti** okno změny. Pokud otevřete soubor kódu (který končí .cs v jazyce Visual C# a vb v jazyce Visual Basic), zobrazí se souboru kódu nebo designer pro souboru kódu. Návrhář je visual prostor, na kterém můžete přidat ovládací prvky, jako jsou tlačítka a seznamy. Pro Visual Studio formuláře se nazývá návrháře Návrhář formulářů Windows.  
  
    -   **Vlastnosti – okno** v tomto okně můžete změnit vlastnosti položek, které zvolíte v dalších oknech. Například pokud se rozhodnete Form1, můžete změnit jeho text nastavením **Text** vlastnost a můžete změnit barvu pozadí nastavením **Backcolor** vlastnost.  
  
    > [!NOTE]
    >  Na začátek řádku **Průzkumníku řešení** ukazuje **řešení "PictureViewer" (1 projekt)**, což znamená, že Visual Studio vytvořilo řešení pro vás. Řešení může obsahovat více než jeden projektu, ale zatím budete pracovat řešení, které obsahují pouze jeden projekt.  
  
6.  Na řádku nabídek zvolte **soubor**, **Uložit vše**.  
  
     Jako alternativu, vyberte **Uložit vše** tlačítka na panelu nástrojů na následujícím obrázku.  
  
     ![Uložit všechny tlačítka panelu nástrojů](../ide/media/express_iconsaveall.png "Express_IconSaveAll")  
Uložit všechny tlačítka panelu nástrojů  
  
     Visual Studio automaticky vyplní název složky a název projektu a pak uloží projekt ve složce projekty.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 2: Spusťte svůj Program](../ide/step-2-run-your-program.md).  
  
-   Přejděte k tématu Přehled, najdete v části [kurzu 1: vytvoření prohlížeče obrázků](../ide/tutorial-1-create-a-picture-viewer.md).