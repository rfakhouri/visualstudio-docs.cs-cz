---
title: "Postupy: Přidání komentářů do pracovního postupu v Návrháři pracovních postupů | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: eb7825f79ee54b02d764e4ad8754ee1382b5d41f
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Postupy: Přidání komentářů do pracovního postupu v Návrháři pracovních postupů

K usnadnění vytváření rozsáhlejších, složitějších pracovních postupů, [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] umožňuje vývojáři přidání poznámky do následující typy položek v Návrháři:

-   <xref:System.Activities.Activity>

-   <xref:System.Activities.Statements.State>

-   <xref:System.Activities.Statements.Transition>

-   Třídy odvozené od <xref:System.Activities.Statements.FlowNode>

-   <xref:System.Activities.Variable>

-   <xref:System.Activities.Argument>

> [!IMPORTANT]
> Obsah poznámky se ukládají jako prostý text k souboru XAML přidružené pracovní postup a může potenciálně číst jiní uživatelé. Buďte opatrní při zadávání citlivé informace do poznámky.

### <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Přidání poznámky do aktivity v Návrháři

1. V Návrháři pracovních postupů, klikněte pravým tlačítkem na položku v pracovním postupu návrháře a vyberte možnost **poznámky**, **přidat poznámky**.

1. Přidejte text anotace v poskytnutém prostoru.

   Položka se zobrazuje ikona poznámky. Ukazatele myši na ikonu poznámky zobrazí text anotace.

### <a name="displaying-an-annotation-in-an-activitys-designer"></a>Zobrazení poznámky v Návrháři aktivity

1.  Návrhář aktivity, který má poznámky zobrazení se mimo aktivity, klikněte na **Pin** ikonu v adorner poznámky.

   Poznámka se zobrazí v Návrháři aktivity. Na tomto snímku obrazovky zobrazí se v Návrháři aktivity poznámky "Počáteční aktivita v pracovním postupu".

   ![Poznámky v Návrháři aktivity zobrazeny](../workflow-designer/media/annotationindesigner.png "AnnotationInDesigner")

1. Pokud chcete zobrazit poznámky mimo Návrhář aktivity, najeďte myší na oblasti poznámky v Návrháři aktivity a klikněte na tlačítko **Odepnout** ikonu

   ![Poznámky zobrazí mimo aktivity designe](../workflow-designer/media/annotationoutsidedesigner.png "AnnotationOutsideDesigner")

### <a name="showing-or-hiding-all-annotations"></a>Zobrazení nebo skrytí všechny poznámky

1. Klikněte pravým tlačítkem na aktivitu, která má poznámky. Vyberte **poznámky**, **zobrazit všechny poznámky**.

   Všechny poznámky se zobrazí v Návrháři aktivity.

1. Pokud chcete zobrazit všechny poznámky mimo Designer aktivity, klikněte pravým tlačítkem na aktivitu a vyberte **poznámky**, **skrýt všechny poznámky**.

### <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Úpravy nebo odstranění poznámky pro aktivitu

1. Klikněte pravým tlačítkem myši na aktivitu, která má poznámky.

1. Vyberte **poznámky**, **upravit poznámky** nebo **odstranit poznámky**.

   Poznámka je po otevření k úpravám nebo odstranit.

1. Pokud chcete odstranit všechny poznámky najednou, klikněte pravým tlačítkem na pracovním postupu návrháře a vyberte možnost **poznámky**, **odstranit všechny poznámky**.

### <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Přidání, úpravy a odstraňování poznámky pro argument nebo proměnná

1. Klikněte pravým tlačítkem na proměnné nebo argumentu a vyberte Přidat poznámky.

1. Zadejte text anotace. Proměnná nebo argument zobrazí ikona poznámky.

1. Klikněte pravým tlačítkem myši na proměnné nebo argument, který má poznámky. Vyberte možnost Upravit poznámky.

   Poznámka je otevřít pro úpravy.

1. Klikněte pravým tlačítkem myši na proměnné nebo argument, který má poznámky. Vyberte možnost Odstranit poznámky.

   Poznámka je odstraněn.