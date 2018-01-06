---
title: "Postupy: Přidání komentářů do pracovního postupu v Návrháři pracovních postupů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
caps.latest.revision: "7"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: e4d547fed57abf11194b35bcd3ac42f12322374b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Postupy: Přidání komentářů do pracovního postupu v Návrháři pracovních postupů
K usnadnění vytváření rozsáhlejších, složitějších pracovních postupů, [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] umožňuje vývojáři přidání poznámky do následující typy položek v Návrháři:  
  
-   <xref:System.Activities.Activity>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
-   Třídy odvozené od<xref:System.Activities.Statements.FlowNode>  
  
-   <xref:System.Activities.Variable>  
  
-   <xref:System.Activities.Argument>  
  
> [!IMPORTANT]
>  Obsah poznámky se ukládají jako prostý text k souboru XAML přidružené pracovní postup a může potenciálně číst jiní uživatelé. Buďte opatrní při zadávání citlivé informace do poznámky.  
  
### <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Přidání poznámky do aktivity v Návrháři  
  
1.  V Návrháři pracovních postupů, klikněte pravým tlačítkem na položku v pracovním postupu návrháře a vyberte možnost **poznámky**, **přidat poznámky**.  
  
2.  Přidejte text anotace v poskytnutém prostoru.  
  
3.  Položka se zobrazí ikona poznámky. Ukazatele myši na ikonu poznámky zobrazí text anotace.  
  
     ![Pořadí aktivit zobrazující poznámky](../debugger/debug-interface-access/annotation.md "– Poznámka")  
  
### <a name="displaying-an-annotation-in-an-activitys-designer"></a>Zobrazení poznámky v Návrháři aktivity  
  
1.  Návrhář aktivity, který má poznámky zobrazení se mimo aktivity, klikněte na **Pin** ikonu v adorner poznámky.  
  
2.  Poznámka se zobrazí v Návrháři aktivity. Na tomto snímku obrazovky zobrazí se v Návrháři aktivity poznámky "Počáteční aktivita v pracovním postupu".  
  
     ![Poznámky v Návrháři aktivity zobrazeny](../workflow-designer/media/annotationindesigner.png "AnnotationInDesigner")  
  
3.  Pokud chcete zobrazit poznámky mimo Návrhář aktivity, najeďte myší na oblasti poznámky v Návrháři aktivity a klikněte na tlačítko **Odepnout** ikonu  
  
     ![Poznámky zobrazí mimo aktivity designe](../workflow-designer/media/annotationoutsidedesigner.png "AnnotationOutsideDesigner")  
  
### <a name="showing-or-hiding-all-annotations"></a>Zobrazení nebo skrytí všechny poznámky  
  
1.  Klikněte pravým tlačítkem na aktivitu, která má poznámky. Vyberte **poznámky**, **zobrazit všechny poznámky**.  
  
2.  Zobrazí se všechny poznámky v Návrháři aktivity.  
  
3.  Pokud chcete zobrazit všechny poznámky mimo Designer aktivity, klikněte pravým tlačítkem na aktivitu a vyberte **poznámky**, **skrýt všechny poznámky**.  
  
### <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Úpravy nebo odstranění poznámky pro aktivitu  
  
1.  Klikněte pravým tlačítkem myši na aktivitu, která má poznámky.  
  
2.  Vyberte **poznámky**, **upravit poznámky** nebo **odstranit poznámky**.  
  
3.  Poznámka bude po otevření k úpravám nebo odstranit.  
  
4.  Pokud chcete odstranit všechny poznámky najednou, klikněte pravým tlačítkem na pracovním postupu návrháře a vyberte možnost **poznámky**, **odstranit všechny poznámky**.  
  
### <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Přidání, úpravy a odstraňování poznámky pro argument nebo proměnná  
  
1.  Klikněte pravým tlačítkem na proměnné nebo argumentu a vyberte Přidat poznámky.  
  
2.  Zadejte text anotace. Proměnná nebo argument se zobrazí ikona poznámky.  
  
3.  Klikněte pravým tlačítkem myši na proměnné nebo argument, který má poznámky. Vyberte možnost Upravit poznámky.  
  
4.  Poznámka bude možné otevřít pro úpravy.  
  
5.  Klikněte pravým tlačítkem myši na proměnné nebo argument, který má poznámky. Vyberte možnost Odstranit poznámky.  
  
6.  Poznámka se odstraní.