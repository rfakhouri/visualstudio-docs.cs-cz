---
title: "Vytvoření vazby ovládacích prvků k obrázkům z databáze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: bc71529f852e87ca206509e06cb80940c11ac36d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Vytvoření vazby ovládacích prvků k obrázkům z databáze
Můžete použít **zdroje dat** okno k navázání obrázku v databázi do ovládacího prvku ve vaší aplikaci. Například můžete vázat bitovou kopii <xref:System.Windows.Controls.Image> řízení v aplikaci WPF nebo na <xref:System.Windows.Forms.PictureBox> ovládací prvek v aplikaci Windows Forms.  
  
Obrázky v databázi se obvykle ukládají jako pole bajtů. Položky v **zdroje dat** okno, které jsou uloženy jako pole bajtů ovládání zadejte nastavit na **žádné** ve výchozím nastavení, protože bajtová pole může obsahovat vše od jednoduchého pole bajtů na spustitelný soubor velké aplikace. Vytvoření ovládacího prvku vázané na data pro položku pole bajtů v **zdroje dat** okně, které představuje bitovou kopii, je nutné vybrat k vytvoření ovládacího prvku.  
  
Následující postup předpokládá, že **zdroje dat** okno je již naplněný položku, která je vázána k bitové kopii. 
  
### <a name="to-bind-a-picture-in-a-database-to-a-control"></a>K vytvoření vazby obrázku v databázi do ovládacího prvku  
  
1.  Ujistěte se, že návrhovou plochu, která chcete přidat do ovládacího prvku je otevřen v Návrháři WPF nebo Návrhář formulářů Windows.  
  
2.  V **zdroje dat** okně Rozbalit požadovanou tabulku nebo objekt zobrazíte její vlastnosti nebo sloupce.  
  
3.  Vyberte sloupec nebo vlastnost, která obsahuje vaše data bitové kopie a jeho ovládacího prvku rozevíracího seznamu vyberte jednu z těchto ovládacích:  
  
    -   Pokud Návrháře WPF je otevřený, vyberte **Image**.  
  
    -   Pokud návrhář formulářů Windows je otevřený, vyberte **PictureBox**.  
  
    -   Alternativně můžete vybrat jiný ovládací prvek, který podporuje datovou vazbu, který může zobrazit obrázky. Pokud není ovládací prvek, který chcete použít v seznamu dostupných ovládacích prvků, můžete ho přidat do seznamu a pak ho vyberte. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
## <a name="see-also"></a>Viz také
[Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)