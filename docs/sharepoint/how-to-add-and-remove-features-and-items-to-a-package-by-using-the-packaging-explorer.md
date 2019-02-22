---
title: 'Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackagingExplorer
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
ms.openlocfilehash: 2dda4193a0ea30ac08f8a63a39ce00fb634832d7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596422"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků
  Pokud chcete nakonfigurovat balíček pro nasazení služby SharePoint položky a funkce, můžete Průzkumníku balíčků. Můžete upravit položky Sharepointového projektu a funkce v souboru WSP.

 Alternativně můžete použít Návrháře balíčku k zobrazení a změna pořadí funkce, které chcete změnit pořadí aktivace. Další informace najdete v tématu [jak: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).

## <a name="open-the-packaging-explorer"></a>Otevřete Průzkumník balení
 Následující postup slouží k otevření Průzkumníku balíčků, pokud řešení sady Visual Studio obsahuje alespoň jeden projekt služby SharePoint. Alternativně Průzkumník balení se automaticky otevře při zobrazení návrháře funkci nebo balíčku. Po zavření všechny funkce a balíku návrháře zavře se také Průzkumníku balíčků.

#### <a name="to-open-the-packaging-explorer"></a>Chcete-li otevřít Průzkumník balení

1.  V panelu nabídky zvolte **zobrazení** > **ostatní Windows** > **Průzkumník balení**.

     **Průzkumník balení** se zobrazí v **nástrojů**.

## <a name="adding-a-feature-to-a-package"></a>Přidání funkce do balíčku
 Nové funkce můžete přidat do balíčku pomocí Průzkumníku balíčků.

#### <a name="to-add-a-sharepoint-feature"></a>Chcete-li přidat funkce služby SharePoint

1.  Otevřete **Průzkumník balení**, otevřete místní nabídku pro projekt a klikněte na tlačítko **přidat funkci**.

#### <a name="to-move-an-existing-sharepoint-feature"></a>Chcete-li přesunout existující funkce Sharepointu

1.  Otevřít **Průzkumník balení**a potom proveďte jednu z následujících kroků:

    -   Přetáhněte **funkce** z jednoho projektu do jiného projektu.

    -   Otevřete místní nabídku pro funkci, zvolte **Vyjmout**, otevřete místní nabídku pro projekt, do kterého chcete přesunout tuto funkci a klikněte na tlačítko **vložit**.

    > [!NOTE]
    >  Tento postup použijte, pokud máte více než jeden projekt služby SharePoint ve vašem řešení.

## <a name="validate-a-feature-or-package"></a>Ověření funkcí nebo balíčku
 Tím, že ověří soubory lze identifikovat případné problémy v součásti služby SharePoint a balíčky. Upozornění a chyby se zobrazují v okně Výstup a v okně Seznam chyb.

#### <a name="to-validate-a-sharepoint-feature-or-package"></a>Ověřit funkce služby SharePoint nebo balíčku

1.  Otevřít **Průzkumník balení**.

2.  Otevřete místní nabídku pro funkci nebo balíček a klikněte na tlačítko **ověřit**.

## <a name="see-also"></a>Viz také:
- [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
