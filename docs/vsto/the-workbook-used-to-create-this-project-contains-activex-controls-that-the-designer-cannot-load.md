---
title: "Sešit použitý k vytvoření tohoto projektu obsahuje ovládací prvky ActiveX, které Návrhář nemůže načíst. | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 0f50342fd82826aec8cf0d9694454afdc2db4080
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>Sešit použitý k vytvoření tohoto projektu obsahuje ovládací prvky ActiveX, které návrhář nemůže načíst.
  Tato chyba se zobrazí při přidání ovládacího prvku na dokument aplikace Word nebo listu aplikace Excel prostřednictvím kódu programu, dokumentu nebo sešit uložit a pak vytvořte nové řešení úrovni dokumentů na základě dokumentu nebo sešitu.  
  
 Informace, které popisují spravovaný typ ovládacího prvku se neuloží společně s dokumentu nebo sešitu. Když vytvoříte nové řešení na základě tohoto dokumentu nebo sešitu, Visual Studio nemá dostatek informací k načtení ovládacího prvku v Návrháři položky hostitele.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Otevřete dokument nebo sešitu.  
  
2.  Odebrání ovládacích prvků, které byly přidány za běhu. To provedete tak, že je vyberete v dokumentu nebo sešitu a stisknutím klávesy DELETE.  
  
3.  Vytvořte řešení úrovni dokumentu v závislosti na dokumentu nebo sešitu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  