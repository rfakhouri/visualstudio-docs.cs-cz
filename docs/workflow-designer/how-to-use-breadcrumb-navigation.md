---
title: 'Návrhář postupu provádění - postupy: použití navigace s popisem cesty'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92f3e35d4182297601741bd603aa3c5a17e54d67
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975063"
---
# <a name="how-to-use-breadcrumb-navigation"></a>Postupy: použití navigace s popisem cesty

Chcete-li změnit sadu aktivit, které se zobrazují v Návrháři pracovních postupů Windows třemi způsoby:

1.  Dvakrát klikněte na panel přejdete podřízené aktivity.

2.  Klikněte na tlačítko na navigačního panelu přejděte do nadřazené aktivity.

3.  Rozbalit nebo sbalit aktivity na místě.

## <a name="using-breadcrumb-navigation"></a>Pomocí navigace s popisem cesty

1.  Dvakrát klikněte na aktivitu Návrháře pracovního postupu, chcete-li změnit kořenový aktivity kliknutelnou aktivity. Kliknutelnou aktivity je pak úplně rozbalit v kořenovém adresáři a jeho předchůdců jsou zobrazeny v navigačním panelu. To se někdy nazývá procházení nebo zrušení aktivity.

2.  Přejděte na nadřazeným aktuální kořenové aktivity, klikněte na aktivitu v navigačním panelu.

## <a name="expanding-or-collapsing-an-activity-in-place"></a>Rozbalení a sbalení aktivitu na místě

1.  Kliknutím na dvojitou šipkou na aktivitu rozbalí či sbalí aktivity v místě.

2.  Při změně stavu stav rozšíření kliknutím na tlačítko Nový stav rozšíření je uložen v jazyce XAML.

    > [!WARNING]
    > Ne všechny aktivity lze rozšířit na místě. Pokud aktivitu nelze rozšířit na místě jsou dva případy: buď nadřazené aktivity neumožňuje své podřízené objekty mají být rozbaleny v místě, (například aktivity v vývojový diagram nelze rozšířit na místě), nebo Návrhář aktivity neumožňuje své vlastní Rozbalit na místě. I když žádný z návrháře aktivit, které jsou zahrnuty v Návrháři pracovních postupů mají pozdější chování, mohou vykazovat některé vlastní aktivity toto chování.

## <a name="expanding-all-or-collapsing-all-activities"></a>Všechny rozbalení a sbalení všechny aktivity.

1.  Použití **Rozbalit vše** a **sbalit všechny** tlačítka v uživatelském rozhraní rozbalit nebo sbalit všechny aktivity v rámci aktuální kořenový adresář s popisem cesty. Všimněte si, že všechny rozbalit nebo sbalit všechny jsou globální stavy. To znamená, že když změníte kořenový aktivity pomocí navigace s popisem cesty, Rozbalit vše nebo sbalit všechny stavy ukládá dokud nekliknete na tlačítko **obnovení**.

2.  Po jste použili Rozbalit vše nebo sbalit všechny stavy, můžete kliknutím **obnovení** tlačítko, které se zobrazí se vrátíte k prohlížení stavu dříve použité pro každou aktivitu.

    > [!WARNING]
    > Pokud aktivity, například <xref:System.Activities.Statements.Flowchart>, má vyjádřit výslovný souhlas mimo rozbalte v místě, funkce související s **Rozbalit vše** a **sbalit všechny** tlačítka je zakázána na **vývojový diagram**  designer. Další informace o **vývojový diagram** návrháře, najdete [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) tématu.

    > [!WARNING]
    > Rozbalit vše má také vliv zvláštní **přepínač** a **TryCatch** návrháře aktivit. Když kliknete na tlačítko **Rozbalit vše**, zobrazí se všechny případy přepínače a všechny bloky try/catch/finally –. Kliknutím na tlačítko **obnovení** nebo **sbalit všechny** vrací tyto designery do výchozího stavu, ve kterém můžete kliknout na jednotlivé případ nebo blok a zobrazte její obsah.