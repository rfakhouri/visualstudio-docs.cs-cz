---
title: "Postupy: vytvoření uživatelského ovládacího prvku pro stránku služby SharePoint aplikace nebo webovou část | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- user controls [SharePoint development in Visual Studio], adding
ms.assetid: 492ea376-7188-4b5a-a2eb-adc0e3f51484
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1c6384ce4437290c0baa5ea1438a0751b4ec1fcf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part"></a>Postupy: Vytvoření uživatelského ovládacího prvku pro stránku aplikace nebo webovou část služby SharePoint
  Můžete také vytvářet vlastní uživatelské ovládací prvky, které poskytují vlastní funkce pro řešení služby SharePoint, a tyto funkce v rámci svého projektu znovu využívat. De webové části nebo do stránky aplikace lze zahrnout uživatelské ovládací prvky, přidat další ovládací prvky technologie ASP.NET, ovládací prvky služby SharePoint a definovat vlastnosti a metody pro ovládací prvek. Další informace o uživatelských ovládacích prvků najdete v tématu [vytváření opakovaně použitelného ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md) a [uživatelské ovládací prvky a ovládací prvky serveru ve službě SharePoint](http://blogs.msdn.com/b/kaevans/archive/2011/04/28/user-controls-and-server-controls-in-sharepoint.aspx).  
  
### <a name="to-create-a-user-control-for-sharepoint"></a>Vytvoření uživatelského ovládacího prvku služby SharePoint.  
  
1.  V aplikaci Visual Studio otevřete nebo vytvořte projekt služby SharePoint.  
  
     V tématu [šablony položek projektu služby SharePoint a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  V **Průzkumníku**, vyberte uzel projektu.  
  
3.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
     **Přidat novou položku** otevře se dialogové okno.  
  
4.  V **nainstalovaná** podokně, vyberte **Office/SharePoint** uzlu.  
  
5.  V seznamu šablon služby SharePoint, zvolte **uživatelský ovládací prvek (pouze řešení farmy)**.  
  
    > [!NOTE]  
    >  Uživatelské ovládací prvky fungují pouze pro řešení farmy.  
  
6.  V **název** pole, zadejte název pro uživatelský ovládací prvek a potom zvolte **přidat** tlačítko.  
  
     Aplikace Visual Studio přidá do projektu několik složek a souborů. Další informace o těchto souborech najdete v tématu [vytváření opakovaně použitelného ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
     Ve výchozím souboru uživatelského ovládacího prvku se zobrazí v **zdroj** zobrazení návrháře Visual Web Developer. V tomto zobrazení lze upravit značku XML ovládacího prvku. Můžete přepnout **návrhu** zobrazit, pokud chcete navrhnout ovládacího prvku vizuálně přetažením ovládacích prvků z **sada nástrojů**. V tématu [návrhu, Designer webových stránek](http://msdn.microsoft.com/en-us/d8f2270a-357d-40a4-9b39-1a3f2366216d).  
  
7.  Pokud chcete zpracovávat události, ke kterým došlo v ovládacím prvku, přidejte kód do souboru kódu uživatelského ovládacího prvku.  
  
     Tento soubor se zobrazí v **Průzkumníku řešení** v souboru uživatelského ovládacího prvku a má příponu cs nebo vb v závislosti na jazyk projektu.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)  
  
  