---
title: "Postupy: zobrazení karty Vývojář na pásu karet | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
ms.assetid: ce7cb641-44f2-4a40-867e-a7d88f8e98a9
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3885ce387aa27857e59fb3af74990d953c047225
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>Postupy: Zobrazení karty Vývojář na pásu karet
  Abyste měli přístup **vývojáře** karty na pásu karet aplikace Office, je nutné nakonfigurovat ji zobrazit tuto kartu, protože se zobrazí ve výchozím nastavení. Například musíte zobrazit dané kartě Pokud chcete přidat <xref:Microsoft.Office.Tools.Word.GroupContentControl> k přizpůsobení na úrovni dokumentu ve Wordu.  
  
> [!NOTE]  
>  Tyto pokyny platí pro Office 2010 nebo novější pouze aplikací. Pokud chcete zobrazit na této kartě v systému Microsoft Office 2007, najdete v následující verzi tohoto tématu [postupy: zobrazení karty Vývojář na pásu karet](http://msdn.microsoft.com/library/bb608625(v=vs.90).aspx).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  Nemá přístup **vývojáře** kartě.  
  
### <a name="to-show-the-developer-tab"></a>K zobrazení karty Vývojář  
  
1.  Spuštění aplikace Office, které jsou podporovány v tomto tématu. Najdete v článku **platí pro:** Poznámka dříve v tomto tématu.  
  
2.  Na **soubor** , zvolte **možnosti** tlačítko.  
  
     Následující obrázek ukazuje **soubor** kartě a **možnosti** tlačítko v Office 2010.  
  
     ![Výběr souborů, možnosti v aplikaci Outlook 2010](../vsto/media/vsto-office-file-tab.png "vyberete soubor, možnosti v aplikaci Outlook 2010")  
  
     Následující obrázek ukazuje **souboru** ve Office 2013.  
  
     ![Karta souboru v aplikaci Outlook 2013](../vsto/media/vsto-office2013-filetab.png "karta soubor v aplikaci Outlook 2013")  
  
     Následující obrázek ukazuje **možnosti** tlačítko v Office 2013.  
  
     ![Tlačítko Možnosti můžete v aplikaci Outlook 2013 Preview](../vsto/media/vsto-office2013-optionsbutton.png "možnosti tlačítko v aplikaci Outlook 2013 Preview")  
  
3.  V *ApplicationName***možnosti** dialogovém okně vyberte **přizpůsobení pásu karet** tlačítko.  
  
     Následující obrázek ukazuje **možnosti** dialogové okno a **přizpůsobení pásu karet** tlačítko v aplikaci Excel 2010. Umístění toto tlačítko je podobný v všechny ostatní aplikace uvedené v části "Platí pro" v horní části tohoto tématu.  
  
     ![Přizpůsobení pásu karet tlačítko](../vsto/media/vsto-office2010-customizeribbonbutton.png "The přizpůsobení pásu karet tlačítko")  
  
4.  V seznamu hlavní karty, vyberte **vývojáře** zaškrtávací políčko.  
  
     Následující obrázek ukazuje **vývojáře** políčko v aplikaci Word 2010 a [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]. Umístění tohoto zaškrtávacího políčka se podobá v všechny ostatní aplikace uvedené v části "Platí pro" v horní části tohoto tématu.  
  
     ![Zaškrtněte políčko vývojáře v dialogovém okně Možnosti v aplikaci Word](../vsto/media/vsto-office2010-developercheckbox.png "Developer zaškrtněte políčko v dialogovém okně Možnosti v aplikaci Word")  
  
5.  Vyberte **OK** tlačítko zavřete **možnosti** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)  
  
  