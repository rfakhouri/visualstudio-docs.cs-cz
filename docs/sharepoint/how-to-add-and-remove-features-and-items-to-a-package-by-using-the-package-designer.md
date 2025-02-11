---
title: 'Návrháři balíčku: Přidání a odebrání funkcí a položek balíčku'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackageDesignerDesign
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fbd44bbf3b337815c8c72cea66dd4d56fc645ade
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66401616"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer"></a>Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků
  Když vytvoříte řešení služby SharePoint, Visual Studio přidá výchozí funkce služby SharePoint do balíčku v řešení. Před posledním nasazení můžete přidávat a odebírat položky Sharepointového projektu a funkce, které chcete upravit balíček Sharepointu.

 Alternativně můžete použít Průzkumník balení přidávat a odebírat položky Sharepointového projektu. Můžete také zobrazit a změnit hierarchie položek projektu služby SharePoint a funkce, které jsou umístěny do balíčku (.wsp). Další informace najdete v tématu [jak: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).

## <a name="add-features-to-a-sharepoint-package"></a>Přidání funkcí do balíčku Sharepointu
 Návrháři balíčku můžete použít k přidání funkcí do balíčku Sharepointu.

#### <a name="to-add-sharepoint-features-with-the-package-designer"></a>Přidání funkcí služby SharePoint pomocí návrháře balíčků

1. Otevřít **balíček návrháře**.

    Další informace najdete v tématu [jak: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).

2. Přidejte jeden nebo více funkcí služby SharePoint pomocí provádí jeden nebo více z následujících kroků:

   1. Dvakrát klikněte na každou položku v **položky v řešení** seznam, který chcete přidat.

   2. Zvolte položku, kterou chcete přidat a potom klikněte **přidat** tlačítko (>).

   3. Zvolte **přidat všechny** tlačítko (>>) Chcete-li přidat všechny položky najednou.

      Například můžete dvakrát kliknout na položku v **položky v řešení** seznamu a přidejte ji tak **položek v balíčku** seznamu.

      Položky projektu služby SharePoint a funkce se zobrazí v **položek v balíčku** seznamu.

## <a name="remove-features-from-a-sharepoint-package"></a>Odebrat funkce z balíčku služby SharePoint
 Návrháři balíčku můžete použít k odebrání funkce pro balíček služby SharePoint.

#### <a name="to-remove-sharepoint-features-with-the-package-designer"></a>Chcete-li odebrat funkce služby SharePoint pomocí návrháře balíčků

1. V **položek v balíčku** seznamu, zvolte položku, kterou chcete odebrat a klikněte na tlačítko **odebrat** (<) tlačítko, nebo zvolte **odebrat všechny** tlačítko (<<) k odebrání všechny položky.

     Položky služby SharePoint se zobrazí v **položky v řešení** seznamu.

## <a name="see-also"></a>Viz také:
- [Vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)
- [Postupy: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)
- [Postupy: Vytvoření balíčku](https://msdn.microsoft.com/b24be45c-e91d-49bb-afb0-7b265404214b)
