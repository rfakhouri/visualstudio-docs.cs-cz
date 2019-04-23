---
title: Používání starší verze návrháře aktivit | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5755c6a3b4ece5b40c7799d83bdf33966d5c2b3e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60070781"
---
# <a name="using-the-legacy-activity-designer"></a>Používání starší verze návrháře aktivit
Toto téma popisuje způsob použití návrháře aktivit v starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Použít starší verzi návrháře při cílení [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Návrhář aktivity umožňuje vytvářet vlastní vlastní aktivity.  
  
## <a name="creating-a-custom-activity"></a>Vytvoření vlastní aktivity  
 Postupujte podle těchto kroků můžete vytvořit vlastní aktivitu pomocí návrháře aktivit:  
  
1. Na **projektu** nabídky, klikněte na tlačítko **přidat aktivitu**.  
  
2. Vyberte **aktivity** nebo **aktivita (s rozdělením kódu)** šablony.  
  
   1. Použití **aktivity** šablony k vytvoření aktivity se definici aktivity a kódem uživatele ve stejném souboru kódu.  
  
   2. Použití **aktivita (s rozdělením kódu)** šablony k vytvoření aktivity s aktivity definicí vyjádřenou jako značka pracovního postupu a kód uživatele v samostatném souboru kódu.  
  
3. Zadejte název aktivity nebo Ponecháme výchozí název a potom klikněte na tlačítko **přidat**.  
  
   Sadu vlastních aktivit můžete vytvořit také tak, že vytvoříte nový projekt typu **knihovny aktivit pracovních postupů**. Další informace o tomto typu projektu naleznete v tématu [jak: Vytvoření knihovny aktivit pracovních postupů (starší verze)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md).  
  
## <a name="configuring-an-activity"></a>Konfigurace aktivity  
 Návrhář aktivity je aktivní, můžete použít prohlížeč vlastností ke konfiguraci vlastností uvedených v následující tabulce.  
  
|Vlastnost|Komentáře|  
|--------------|--------------|  
|**Název**|Název aktivity.|  
|**Základní třída**|Základní třída, která je odvozena z aktivity. Výchozí základní třída je [aktivitu typu SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). V **vlastnosti** okna, klikněte na tlačítko **základní třída** symbol tří teček **[...]**  k výběru jiné základní třídy v [Procházet a vybrat typ dialogovému oknu rozhraní .NET (starší verze)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md).|  
|**Popis**|Uživatelsky definovaný popis aktivity.|  
|**Povoleno**|Nastavte na **True** ve výchozím nastavení k povolení spuštění aktivit a ověřování. Nastavte na **False** zakázat provádění aktivity a ověřování. Informace o spuštění aktivit a ověřování najdete v tématu [vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65024).|  
  
## <a name="adding-child-activities"></a>Přidání podřízených aktivit  
 Podřízené aktivity můžete přetáhnout z panelu nástrojů na aktivitu, která při návrhu. Potom můžete nakonfigurovat každou podřízenou aktivitu pomocí prohlížeče vlastností.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65024)   
 [Vytváření vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65021)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)   
 [Ukázky vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65022)   
 [Postupy: Vytvoření knihovny aktivit pracovních postupů (starší verze)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)   
 [Používání starší verze návrháře postupu provádění](../workflow-designer/using-the-legacy-workflow-designer.md)