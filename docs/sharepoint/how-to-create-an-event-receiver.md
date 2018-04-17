---
title: 'Postupy: vytvoření přijímače událostí | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.EventReceiver
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ead81e01022c8f389ad6010c89d0e433b82c542e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-event-receiver"></a>Postupy: Vytvoření přijímače událostí
  Vytvořením *přijímače událostí*, reagovat, když uživatel komunikuje se službou SharePoint – položky například seznamy nebo položky seznamu. Kód v přijímače událostí například můžete spustit, když uživatel změní kalendáře nebo odstraní název ze seznamu kontaktů. Pomocí následujících Toto téma, můžete informace o postupu přidání přijímače událostí do seznamu instance.  
  
 K provedení těchto kroků, je třeba nainstalovat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a podporované edice systému Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md). Protože tento příklad vyžaduje projektu služby SharePoint, je také nutné provést podle postupu v tématu [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
## <a name="adding-an-event-receiver"></a>Přidání přijímače událostí  
 Projekt, který jste vytvořili v [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) zahrnuje sloupce vlastního webu, vlastní seznam a typu obsahu. V následujícím postupu budete tento projekt rozšířit přidáním jednoduchá událost obslužná rutina (příjemce událostí) do instance seznamu zobrazíte zpracování událostí, ke kterým došlo v SharePoint – položky například seznamy.  
  
#### <a name="to-add-an-event-receiver-to-the-list-instance"></a>Chcete-li přidat příjemce událostí k instanci seznamu  
  
1.  Otevřete projekt, který jste vytvořili v [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
2.  V **Průzkumníku řešení**, vyberte uzel projektu služby SharePoint, která se nazývá **Klinika**.  
  
3.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
4.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** položky.  
  
5.  V **šablony** podokně vyberte **příjemce událostí**, pojmenujte ji **TestEventReceiver1**a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
6.  V **jaký typ příjemce událostí chcete?** vyberte **události položky seznamu**.  
  
7.  V **co položka by měl být zdroj události?** vyberte **pacientů (Clinic\Patients)**.  
  
8.  V **zpracovávat následující události** seznamu, zaškrtněte políčko vedle **přidání položky**a potom zvolte **Dokončit** tlačítko.  
  
     Soubor s kódem pro nové příjemce událostí obsahuje jednu metodu s názvem `ItemAdded`. V dalším kroku přidáte kód pro tuto metodu tak, aby každý kontakt budou pojmenované Scott menších ve výchozím nastavení.  
  
9. Nahradit existující `ItemAdded` metoda s následující kód a potom vyberte klávesy F5:  
  
     [!code-csharp[SP_EventReceiver#1](../sharepoint/codesnippet/CSharp/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../sharepoint/codesnippet/VisualBasic/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]  
  
     Spustí kód a SharePoint Server se zobrazí ve webovém prohlížeči.  
  
10. Na panel Rychlé spuštění, zvolte **pacientů** propojit a potom zvolte **přidat novou položku** odkaz.  
  
     Otevře se formuláře pro nové položky.  
  
11. Do polí zadejte data a potom vyberte **Uložit** tlačítko.  
  
     Po kliknutí **Uložit** tlačítko **pacienta název** sloupec automaticky aktualizuje na název Scott menších.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  