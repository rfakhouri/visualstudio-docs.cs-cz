---
title: "Pomocí návrháře starší aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: d8288db6ddca4041a409b435ccd730d0b15b013b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-legacy-activity-designer"></a>Pomocí návrháře starší aktivity
Toto téma popisuje, jak používat návrháře aktivit v starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Použít starší verzi návrháře při cílení [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Návrhář aktivity umožňuje vytvářet vlastní aktivitu.  
  
## <a name="creating-a-custom-activity"></a>Vytváření vlastních aktivit  
 Postupujte podle těchto kroků můžete vytvořit vlastní aktivity pomocí návrháře aktivity:  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat aktivitu**.  
  
2.  Vyberte **aktivity** nebo **aktivity (s odděleným kódem)** šablony.  
  
    1.  Použití **aktivity** šablony k vytvoření aktivity se definici aktivity a uživatelského kódu ve stejném souboru kódu.  
  
    2.  Použití **aktivity (s odděleným kódem)** šablony k vytvoření aktivity se definici aktivity, vyjádřené jako značka pracovního postupu a uživatelského kódu v samostatném souboru kódu.  
  
3.  Zadejte název aktivity nebo ponechejte výchozí název a potom klikněte na **přidat**.  
  
 Můžete také vytvořit sadu vlastní aktivity tak, že vytvoříte nový projekt typu **knihovny aktivit pracovních postupů**. Další informace o tomto typu projektu najdete v tématu [postupy: vytvoření knihovny aktivit pracovních postupů (zastaralé)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md).  
  
## <a name="configuring-an-activity"></a>Konfigurace aktivity  
 Zatímco Návrhář aktivity je aktivní, můžete prohlížeč vlastností konfigurace vlastností uvedených v následující tabulce.  
  
|Vlastnost|Komentáře|  
|--------------|--------------|  
|**Jméno**|Název aktivity.|  
|**Base – třída**|Základní třídy, která je odvozena z aktivity. Výchozí základní třída má [SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). V **vlastnosti** okně klikněte **základní třída** třemi tečkami **[...]**  vybrat jiné základní třídy v [Procházet a vybrat .NET typ dialogové okno (zastaralé)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md).|  
|**Popis**|Uživatelem definovaný popis aktivity.|  
|**Povoleno**|Nastavte na **True** ve výchozím nastavení k povolení spuštění aktivity a ověření. Nastavte na **False** zakázat provedení aktivity a ověření. Informace o spouštění aktivity a ověření najdete v tématu [vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65024).|  
  
## <a name="adding-child-activities"></a>Přidání podřízené aktivity  
 Můžete přetáhnout podřízené aktivity z panelu nástrojů pro aktivitu, která návrhu. Pak můžete nakonfigurovat každou aktivitu podřízené pomocí prohlížeče vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65024)   
 [Vytváření vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65021)   
 [Aktivity pracovního postupu starší verze](../workflow-designer/legacy-workflow-activities.md)   
 [Ukázky vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65022)   
 [Postupy: vytvoření knihovny aktivit pracovních postupů (zastaralé)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)   
 [Používání starší verze návrháře postupu provádění](../workflow-designer/using-the-legacy-workflow-designer.md)