---
title: 'Návrhář postupu provádění - postupy: vytvoření Knihovna návrháře aktivit'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d05ddb48e88627f4b7ab4112c164b5129ddba910
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-activity-designer-library"></a>Postupy: vytvoření Knihovna návrháře aktivit
Návrháři vlastních aktivit umožňují vytváření uživatelského rozhraní pro standardní nebo vlastní aktivity. Řízení složitosti uživatelské rozhraní a mít možnost vytvořit více než jeden návrhář aktivity pro aktivitu. Tento scénář vám umožní vytvořit návrhářů, které jsou přizpůsobené pro více publik.

## <a name="to-create-an-activity-designer-library"></a>Chcete-li vytvořit knihovnu Návrhář aktivity

1.  Spusťte sadu Visual Studio 2010.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu** otevřete **nový projekt** dialogové okno.

3.  V **typy projektů** podokně, vyberte **pracovního postupu** buď z **Visual C#** nebo **jazyka Visual Basic** seskupení v závislosti na upřednostňovanou jazyk.

4.  V **šablony** podokně, vyberte **knihovny návrháře aktivit**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** pole, zadejte popisný název pro vaše řešení a pak klikněte na tlačítko **OK**.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v sadě Visual Studio 2010, klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak **Nový projekt** otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici návrháře aktivit v XAML a soubor implementace kódu ve zdrojovém kódu. Návrháři pracovních postupů Windows se zobrazí na plátno pro vaše Návrhář aktivity.

9. Ovládací prvky přetažení Windows Presentation Foundation (WPF) z **sada nástrojů** na návrhovou plochu jejich použití v Návrháři vaše vlastní aktivity.  Příklad implementace vlastního návrháře aktivit, naleznete v části [postupy: vytvoření vlastní Návrhář aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer).

    > [!WARNING]
    > Návrháři vlastních aktivit lze použít pro vlastní aktivity, stejně jako u rozhraní .NET Framework 4activities výchozí.

## <a name="see-also"></a>Viz také

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)