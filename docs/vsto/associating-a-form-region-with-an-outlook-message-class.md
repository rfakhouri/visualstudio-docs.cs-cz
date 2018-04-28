---
title: Přidružení oblasti formuláře k třídě zpráv aplikace Outlook | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e3e3deeb55fb93b1a393d0489213f1d0e7acd85b
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
---
# <a name="associating-a-form-region-with-an-outlook-message-class"></a>Přidružení oblasti formuláře k třídě zpráv aplikace Outlook
  Můžete určit, které aplikace Microsoft Office Outlook položky zobrazení oblasti formuláře ve přidružení oblasti formuláře k třídě zpráv každé položky. Například pokud se chcete připojit oblasti formuláře k dolnímu okraji položku e-mailu, můžete přidružit oblasti formuláře IPM. Poznámka: Třída zprávy.  
  
 Přidružení oblasti formuláře s třídou zprávy, zadat název třídy zpráv v **nové oblasti formuláře aplikace Outlook** průvodce nebo použít atribut třídu objektů factory oblasti formuláře.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understanding-outlook-message-classes"></a>Vysvětlení tříd zpráv aplikace Outlook  
 Třídě zpráv aplikace Outlook identifikuje typ položky aplikace Outlook. Následující tabulka uvádí tyto osm standardní typy položek a jejich názvy tříd zprávy.  
  
|Typ položky aplikace Outlook|Název třídy zpráv|  
|-----------------------|------------------------|  
|Částí AppointmentItem|IPM. Událost|  
|ContactItem|IPM. Obraťte se na|  
|DistListItem|IPM. DistList|  
|JournalItem|IPM. Aktivity|  
|MailItem|IPM. Poznámka:|  
|PostItem|IPM. Metoda POST nebo IPM. Post.RSS|  
|TaskItem|IPM. Úloha|  
  
 Můžete také zadat názvy tříd vlastní zpráv. Třídy vlastní zprávu při identifikaci vlastních formulářích, které definujete v aplikaci Outlook.  
  
> [!NOTE]  
>  Pro nahrazení a oblastí formulářů nahradit všechny můžete zadejte nový název třídy vlastní zprávu. Není nutné používat název třídy zpráva existující vlastní formulář. Název třídy vlastní zprávy musí být jedinečný. Zajistěte, aby byl název jedinečný jedním ze způsobů je použít zásady vytváření názvů podobný následujícímu: \< *StandardMessageClassName*>.\< *Společnosti*>.\< *MessageClassName*> (například: IPM. Note.Contoso.MyMessageClass).  
  
## <a name="associating-a-form-region-with-an-outlook-message-class"></a>Přidružení oblasti formuláře k třídě zpráv aplikace Outlook  
 Přidružení oblasti formuláře s třídou zprávy dvěma způsoby:  
  
-   Použití **nové oblasti formuláře aplikace Outlook** průvodce.  
  
-   Použití třídy atributů.  
  
### <a name="using-the-new-outlook-form-region-wizard"></a>Pomocí nového Průvodce oblasti formuláře aplikace Outlook  
 Na poslední stránce **nové oblasti formuláře aplikace Outlook** průvodce, můžete vybrat tříd standardní zpráv a zadejte názvy tříd vlastní zpráv, které chcete přidružit k oblasti formuláře.  
  
 Standardní zprávy třídy nejsou k dispozici, pokud oblasti formuláře je určena k nahrazení celého formuláře nebo výchozí stránka formuláře. Můžete zadat názvy tříd standardní zprávy pouze pro formuláře přidá novou stránku do formuláře nebo které se připojují k dolnímu okraji formuláře. Další informace najdete v tématu [postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Chcete-li zahrnout jeden nebo více tříd, vlastní zprávu, zadejte jejich názvy v **které třídy vlastní zpráva se zobrazí tato oblasti formuláře?** pole.  
  
 Názvy, které zadáte, musí splňovat následující pokyny:  
  
-   Použít zpráva plně kvalifikovaný název třídy (například: "IPM. Note.Contoso").  
  
-   K oddělení více názvy tříd zprávy použijte středníky.  
  
-   Nezahrnovat standardní tříd zpráv aplikace Outlook, jako je například "IPM. Poznámka:"nebo"IPM. Obraťte se na". Zahrňte pouze vlastní zprávu třídy, jako je například "IPM. Note.Contoso".  
  
-   Nezadávejte třídu základní zpráv samostatně (například: "IPM").  
  
-   Není delší než 256 znaků pro každý název třídy zpráv.  
  
 **Nové oblasti formuláře aplikace Outlook** Průvodce ověří formát váš vstup, po kliknutí na tlačítko **Dokončit**.  
  
> [!NOTE]  
>  **Nové oblasti formuláře aplikace Outlook** průvodce není ověřte, zda jsou názvy tříd zprávy, které zadáte správnou nebo platný.  
  
 Po dokončení průvodce, **nové oblasti formuláře aplikace Outlook** průvodce platí atributy pro třídu oblasti formuláře, která obsahovat názvy tříd zadané zprávy. Tyto atributy můžete použít také ručně.  
  
### <a name="applying-class-attributes"></a>Použití atributů – třída  
 Po dokončení, budete moct přidružit oblasti formuláře k třídě zpráv aplikace Outlook **nové oblasti formuláře aplikace Outlook** průvodce. K tomu Použíjte atributy pro třídu objektů factory oblasti formuláře.  
  
 Následující příklad ukazuje dva <xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute> atributy, které byly použity na třídu objektu pro vytváření oblasti formuláře s názvem `myFormRegion`. První atribut přidruží oblasti formuláře třída standardní zprávy pro formulář zprávy e-mailu. Druhý atribut přidruží oblasti formuláře třídy vlastní zprávu s názvem `IPM.Task.Contoso`.  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 Atributy musí dodržovat následující pokyny:  
  
-   Pro třídy vlastní zprávu, použijte zpráva plně kvalifikovaný název třídy (například: "IPM. Note.Contoso").  
  
-   Nezadávejte třídu základní zpráv samostatně (například: "IPM").  
  
-   Není delší než 256 znaků pro každý název třídy zpráv.  
  
-   Pokud oblasti formuláře nahradí celý formulář nebo výchozí stránka s formuláře nebudou obsahovat názvy tříd standardní zpráv. Můžete zadat názvy tříd standardní zprávy pouze pro formuláře přidá novou stránku do formuláře nebo které se připojují k dolnímu okraji formuláře. Další informace najdete v tématu [postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Visual Studio ověří formát názvy tříd zprávy při sestavování projektu.  
  
> [!NOTE]  
>  Visual Studio není ověřte, zda jsou názvy tříd zprávy, které zadáte správnou nebo platný.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Název formuláře a přehledu třídy zpráv](http://msdn.microsoft.com/library/office/ff867629.aspx)   
 [Jak spolupracují formulářů aplikace Outlook a položek](http://msdn.microsoft.com/library/office/ff869706.aspx)  
  
  