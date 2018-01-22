---
title: "Okno sady nástrojů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
f1_keywords:
- vs.toolbox.general
- vs.toolbox
helpviewer_keywords:
- Toolbox [Visual Studio]
- custom controls [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 50c9cc96d501eb6d7d10ab31f48600eb65eb57a7
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="toolbox"></a>Sada nástrojů

**Sada nástrojů** okno zobrazí ovládací prvky, které můžete přidat do projektů sady Visual Studio. Chcete-li otevřít sady nástrojů, zvolte **sada nástrojů** na **zobrazení** nabídky.

![Okna nástrojů](media/toolbox.png)

Můžete přetáhnout a vyřadit různých ovládacích prvků na plochu návrháře používají a změnit velikost a umístění ovládacích prvků.

Sada nástrojů objeví ve spojení s návrháře zobrazení, jako je například návrháře zobrazení souboru XAML. Sada nástrojů zobrazí pouze tyto ovládací prvky, které lze použít v Návrháři aktuální. Můžete hledat v rámci nástrojů pro další filtrování položek, které se zobrazují.

> [!NOTE]
> Pro některé typy projektů sady nástrojů nemusí zobrazit všechny položky.

Verze rozhraní .NET Framework, že cílem vašeho projektu je také ovlivňuje sadu ovládacích prvků, které jsou viditelné v sadě nástrojů. Můžete nastavit projektu pro jinou verzi rozhraní .NET Framework ze stránky vlastností projektu. Vyberte uzel projektu v **Průzkumníku řešení**a potom na panelu nabídek vyberte **projektu** > **\<projektu\> vlastnosti**. Na **aplikace** pomocí **cílové rozhraní** rozevíracího seznamu.

## <a name="managing-the-toolbox-window-and-its-controls"></a>Správa okna nástrojů a jeho ovládacích prvků

Ve výchozím nastavení se sada nástrojů sbalena na levé straně Visual Studio IDE a se zobrazí, když je přesunut kurzor. Budete moct připnout sady nástrojů (kliknutím **Pin** ikonu na panelu nástrojů) tak, aby zůstane otevřený po přesunutí kurzoru. Můžete také uvolnit okno sady nástrojů a přetáhněte ji na libovolné místo na obrazovce. Lze ukotvit, vyjměte a skrytí nástrojů pravým tlačítkem myši na jeho panelu nástrojů a výběrem jedné z možností.

Můžete změnit pořadí položek na kartě nástrojů nebo přidat vlastní karty a položek pomocí následujících příkazů v místní nabídce:

- **Přejmenovat položku** -Přejmenuje vybranou položku.

- **Zobrazit všechny** -zobrazuje všechny možné ovládací prvky (nikoli pouze ty, které se vztahují k aktuální designer).

- **Zobrazení seznamu** -zobrazuje ovládacích prvků ve svislém seznamu. Pokud není zaškrtnuto, zobrazí se vodorovně ovládacích prvků.

- **Zvolte položky** -otevře **výběr položek sady nástrojů** pole, ve kterém můžete zadat položky, které se zobrazují v **sada nástrojů**. Můžete zobrazit nebo skrýt položku zaškrtnutím nebo zrušením zaškrtnutí jejího políčka.

- **Seřazení položek abecedně** -Seřadí položky podle názvu.

- **Panel nástrojů obnovit** – obnoví výchozí nastavení sady nástrojů a položky.

- **Přidat kartu** -přidá novou kartu panelu nástrojů.

- **Přesunout nahoru** -Přesune vybranou položku nahoru.

- **Přesunout dolů** -Přesune vybranou položku dolů.

## <a name="creating-and-distributing-custom-toolbox-controls"></a>Vytváření a distribuci vlastní ovládací prvky panelu nástrojů

Můžete vytvořit vlastní ovládací prvky sady nástrojů, buď pomocí šablony projektu, který je založen na spuštění [Windows Presentation Foundation](../../extensibility/creating-a-wpf-toolbox-control.md) nebo na [Windows Forms](../../extensibility/creating-a-windows-forms-toolbox-control.md). Potom můžete distribuovat vlastního ovládacího prvku do ostatními členy týmu, nebo publikování na webu pomocí [instalační program sady nástrojů ovládacích prvků](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="help-on-toolbox-tabs"></a>Nápovědy na kartách sada nástrojů

Následující témata obsahují další informace o některé z dostupných **sada nástrojů** karty.

- [Panel nástrojů, karta Data](../../ide/reference/toolbox-data-tab.md)

- [Panel nástrojů, karta Součásti](../../ide/reference/toolbox-components-tab.md)

- [Panel nástrojů, karta HTML](../../ide/reference/toolbox-html-tab.md)
