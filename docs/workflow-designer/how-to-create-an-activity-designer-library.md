---
title: 'Postupy: vytvoření Knihovna návrháře aktivit | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0dc336db00f8a638cf20e6af79f2cf7ec030a5f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-activity-designer-library"></a>Postupy: vytvoření Knihovna návrháře aktivit
Návrháři vlastních aktivit umožňují vytváření uživatelského rozhraní pro standardní nebo vlastní aktivity. Řízení složitosti uživatelské rozhraní a mít možnost vytvořit více než jeden návrhář aktivity pro aktivitu. Tento scénář vám umožní vytvořit návrhářů, které jsou přizpůsobené pro více publik.

### <a name="to-create-an-activity-designer-library"></a>Chcete-li vytvořit knihovnu Návrhář aktivity

1.  Spustit [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu...**  otevřete **nový projekt** dialogové okno.

3.  V **typy projektů** podokně, vyberte **pracovního postupu** buď z **Visual C#** nebo **jazyka Visual Basic** seskupení v závislosti na upřednostňovanou jazyk.

4.  V **šablony** podokně, vyberte **knihovny návrháře aktivit**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** pole, zadejte popisný název pro vaše řešení a pak klikněte na tlačítko **OK**.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak **Nový projekt...**  otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici návrháře aktivit v XAML a soubor implementace kódu ve zdrojovém kódu. Návrháři pracovních postupů Windows se zobrazí na plátno pro vaše Návrhář aktivity.

9. Přetáhněte [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)] z ovládací prvky **sada nástrojů** na návrhovou plochu jejich použití v Návrháři vaše vlastní aktivity.  Příklad implementace vlastního návrháře aktivit, naleznete v části [postupy: vytvoření vlastní Návrhář aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer).

    > [!WARNING]
    > Návrháři vlastních aktivit lze použít pro vlastní aktivity, stejně jako u výchozí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]aktivity.

## <a name="see-also"></a>Viz také

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)