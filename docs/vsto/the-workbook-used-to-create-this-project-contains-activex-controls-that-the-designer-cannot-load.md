---
title: Sešit použitý k vytvoření tohoto projektu obsahuje ovládací prvky ActiveX, které návrhář nemůže načíst.
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0087841e7f37d49da40817e1487b8529af1f87df
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978924"
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>Sešit použitý k vytvoření tohoto projektu obsahuje ovládací prvky ActiveX, které návrhář nemůže načíst.
  Tato chyba se zobrazí, pokud přidáte ovládací prvek do Wordového dokumentu nebo listu aplikace Excel prostřednictvím kódu programu uložit dokumentem nebo sešitem a pak vytvořte nové úrovni dokumentu řešení na základě dokumentu nebo sešitu.

 Informace, které popisují spravovaného typu ovládacího prvku se neuloží, spolu s dokumentem nebo sešitem. Při vytváření nového řešení založeného na tomto dokumentu nebo sešitu sady Visual Studio nemá dostatek informací, které načíst ovládací prvek v návrháři pro položku hostitele.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Otevření dokumentu nebo sešitu.

2. Odebrání ovládacích prvků, které byly přidány za běhu. Můžete to provést tak, že je vyberete v dokumentu nebo sešitu a stisknutím klávesy **odstranit** klíč.

3. Vytvořte úrovni dokumentu řešení na základě dokumentu nebo sešitu.

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
