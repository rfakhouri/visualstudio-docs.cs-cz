---
title: 'Návrhář postupu provádění – jak: Používání navigace s popisem cesty'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de1004dd7a62fe4163147db4928783dd9a0dca98
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949497"
---
# <a name="how-to-use-breadcrumb-navigation"></a>Postupy: Používání navigace s popisem cesty

Chcete-li změnit sadu aktivit, které se zobrazí v Návrháři postupu provádění třemi způsoby:

1. Dvakrát klikněte na Přejít k podřízené aktivity.

2. Klikněte na tlačítko na panelu navigace s popisem cesty a přejděte na nadřazenou aktivitou.

3. Rozbalit nebo sbalit aktivity na místě.

## <a name="using-breadcrumb-navigation"></a>Pomocí navigace s popisem cesty

1. Dvakrát klikněte na aktivitu pracovního postupu návrháře změna kořenové aktivity na kliknutí na aktivity. Kliknutí na aktivity se pak úplně rozbalit v kořenovém adresáři a jeho nadřazenými prvky jsou uvedeny na panelu navigace s popisem cesty. To se někdy nazývá procházení nebo z aktivity.

2. Pokud chcete přejít na nadřazena aktuální kořenové aktivity, klikněte na aktivitu v panelu s popisem cesty.

## <a name="expanding-or-collapsing-an-activity-in-place"></a>Rozbalení a sbalení aktivitu na místě

1. Kliknutím na dvojité šipky pro aktivitu rozbalí nebo sbalí aktivity na místě.

2. Při změně stavu stavu rozbalení kliknutím na tlačítko Nový stav rozšíření je uložen v XAML.

    > [!WARNING]
    > Ne všechny aktivity lze rozšířit na místě. Existují dva možné případy, kdy aktivita nelze rozšířit na místě: buď nadřazené aktivity nepovoluje své podřízené objekty rozbalen v místě, (například aktivity ve vývojovém diagramu nelze rozšířit na místě), nebo Návrhář aktivity neumožňuje samotného Rozbalit na místě. I když žádný z návrhářů aktivit v Návrháři postupu provádění nemá druhé chování, některé vlastní aktivity může tímto způsobem chovat.

## <a name="expanding-all-or-collapsing-all-activities"></a>Všechny rozbalení nebo sbalení všech aktivit

1. Použití **Rozbalit vše** a **Sbalit vše** tlačítka v uživatelském rozhraní pro rozbalení a sbalení všech aktivit v kořenovém adresáři aktuální navigace s popisem cesty. Všimněte si, že všechny rozbalit nebo sbalit všechny jsou globální stavy. To znamená, že když změníte kořenové aktivity pomocí navigace s popisem cesty, Rozbalit vše nebo sbalit všechny stavy opakuje dokud nekliknete na tlačítko **obnovení**.

2. Po použily všechny rozbalit nebo sbalit všechny stavy, můžete klepnout **obnovení** tlačítko, které se zobrazí chcete přejít zpátky k prohlížení stavu dříve použít u každé aktivity.

    > [!WARNING]
    > Pokud aktivitu, například <xref:System.Activities.Statements.Flowchart>, zvolil z rozbalit na místě, přidružený k funkci **Rozbalit vše** a **Sbalit vše** tlačítka je zakázán na **vývojový diagram**  návrháře. Další informace o **vývojový diagram** návrháře, viz [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) tématu.

    > [!WARNING]
    > Rozbalit vše má také zvláštní efekt v **přepínač** a **TryCatch** návrháři aktivit. Po kliknutí na **Rozbalit vše**, zobrazí se všechny switch case a všechny bloky konstrukce try/catch/finally. Kliknutím na **obnovení** nebo **Sbalit vše** vrací tyto návrháře do výchozího stavu, ve kterém můžete kliknout na jednotlivé případ nebo blok a zobrazit jeho obsah.