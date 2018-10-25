---
title: Vytvoření pravidel nástroje Analýza kódu vlastní nastavení v sadě Visual Studio
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dce43c02f4976b51bab61a48f615fb0307102fc7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49884183"
---
# <a name="customize-a-rule-set"></a>Přizpůsobení sady pravidel

Můžete vytvořit vlastní sadu pravidel, která podle potřeb konkrétního projektu pro analýzu kódu.

## <a name="create-a-custom-rule-set"></a>Vytvoření vlastní sady pravidel

Chcete-li vytvořit vlastní pravidlo nastavte, můžete otevřít sadu předdefinovaných pravidel **s editorem sad pravidel**. Odtud můžete přidat nebo odebrat konkrétní pravidla a akce, která nastane, pokud došlo k porušení pravidla můžete změnit&mdash;například zobrazit upozornění nebo chybu.

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a pak vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýzy kódu** kartu.

3. V **spustit tuto sadu pravidel** rozevíracího seznamu, proveďte jednu z následujících akcí:

   - Vyberte sadu pravidel, který chcete přizpůsobit.

     \- nebo –

   - Vyberte  **\<Procházet... >** zadat sadu existujících pravidel, která se nenachází v seznamu.

4. Vyberte **otevřít** zobrazíte pravidla v editoru sad pravidel.

Můžete také vytvořit nový soubor sady pravidel z **nový soubor** dialogové okno:

1. Vyberte **souboru** > **nový** > **souboru**, nebo stiskněte klávesu **Ctrl**+**N**.

2. V **nový soubor** dialogové okno, vyberte **Obecné** kategorii na levé straně a pak vyberte **sady pravidel analýzy kódu**.

3. Vyberte **otevřít**.

   Nové *.ruleset* soubor se otevře v editoru sad pravidel.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>Vytvoření vlastního pravidla nastavit z více sad pravidel

1. V Průzkumníku řešení klikněte pravým tlačítkem myši na projekt a pak vyberte **vlastnosti**.

2. Na **vlastnosti** stránky, vyberte **analýzy kódu** kartu.

3. Vyberte  **\<zvolit sady více pravidel... >** z **spustit tuto sadu pravidel**.

4. V **přidat nebo odebrat sady pravidel** dialogové okno, vyberte pravidlo sad, které chcete zahrnout do nové sady pravidel.

   ![Přidání nebo odebrání dialogové okno sady pravidel](media/add-remove-rule-sets.png)

5. Vyberte **uložit jako**, zadejte název *.ruleset* souboru a pak vyberte **Uložit**.

   Nová sada pravidel je vybrán v **spustit tuto sadu pravidel** seznamu.

6. Vyberte **otevřete** otevřete novou sadu pravidel v editoru sad pravidel.

## <a name="name-and-description"></a>Název a popis

Chcete-li změnit zobrazovaný název sady pravidel, která je otevřená v editoru, otevřete **vlastnosti** okna tak, že vyberete **zobrazení** > **okno vlastností** na řádku nabídek. Zadejte zobrazovaný název v **název** pole. Můžete také zadat popis sady pravidel.

## <a name="next-steps"></a>Další kroky

Teď, když máte sadu pravidel, dalším krokem je přizpůsobit pravidla přidávání nebo odstraňování pravidel nebo úpravou závažnost porušení pravidel.

> [!div class="nextstepaction"]
> [Úprava pravidel v editoru sad pravidel](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>Viz také:

- [Postupy: Konfigurace Analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)