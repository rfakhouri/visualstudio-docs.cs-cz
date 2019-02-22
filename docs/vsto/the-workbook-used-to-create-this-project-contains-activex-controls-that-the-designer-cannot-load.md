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
ms.openlocfilehash: 8c6c51e464a3c4c49d4c70e4012df47906244804
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56638189"
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>Sešit použitý k vytvoření tohoto projektu obsahuje ovládací prvky ActiveX, které návrhář nemůže načíst.
  Tato chyba se zobrazí, pokud přidáte ovládací prvek do Wordového dokumentu nebo listu aplikace Excel prostřednictvím kódu programu uložit dokumentem nebo sešitem a pak vytvořte nové úrovni dokumentu řešení na základě dokumentu nebo sešitu.

 Informace, které popisují spravovaného typu ovládacího prvku se neuloží, spolu s dokumentem nebo sešitem. Při vytváření nového řešení založeného na tomto dokumentu nebo sešitu sady Visual Studio nemá dostatek informací, které načíst ovládací prvek v návrháři pro položku hostitele.

## <a name="to-correct-this-error"></a>Oprava této chyby

1.  Otevření dokumentu nebo sešitu.

2.  Odebrání ovládacích prvků, které byly přidány za běhu. Můžete to provést tak, že je vyberete v dokumentu nebo sešitu a stisknutím klávesy **odstranit** klíč.

3.  Vytvořte úrovni dokumentu řešení na základě dokumentu nebo sešitu.

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
