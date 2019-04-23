---
title: 'Postupy: Přidání aktivit do panelu nástrojů (starší verze) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- Toolbox, adding activities
- activities, adding to Toolbox
ms.assetid: b66ea29c-120b-40ba-8a61-c1c8240850fa
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c3a8c6f397bbafdbdb29ecbb193c4200a26335c3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60089325"
---
# <a name="how-to-add-activities-to-the-toolbox-legacy"></a>Postupy: Přidání aktivit do panelu nástrojů (starší verze)
Při vytváření řešení pracovního postupu s starší [!INCLUDE[wfd1](../includes/wfd1-md.md)] , který cílí [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)], vlastní aktivity mohou být přidány do projektu pracovního postupu a jejich návrháři umístěny do **nástrojů** pro snadné přístup. Můžete také přidat aktivity přímo **nástrojů** z dynamické knihovny (DLL).  
  
### <a name="to-add-an-activity-to-the-toolbox-from-a-dll"></a>Chcete-li přidat aktivitu do panelu nástrojů z knihovny DLL  
  
1. Klikněte pravým tlačítkem na plochu okna nástrojů v rámci **pracovního postupu Windows**a potom klikněte na tlačítko **zvolit položky**.  
  
2. V **zvolit položky nástrojů** dialogové okno, klikněte na tlačítko **komponenty System.Activities** kartu a potom klikněte na tlačítko **Procházet** z dolní pravé části okna.  
  
3. Vyberte knihovnu DLL z adresáře souboru, který obsahuje implementaci vlastní aktivitu pro přidání do **nástrojů**a potom klikněte na tlačítko **otevřít**.  
  
4. Klikněte na tlačítko **OK** mohli dokončit přidávání aktivity do panelu nástrojů.  
  
## <a name="see-also"></a>Viz také  
 [Používání starší verze návrháře aktivit](../workflow-designer/using-the-legacy-activity-designer.md)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)