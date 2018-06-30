---
title: 'Postupy: vytvoření uživatelského ovládacího prvku pro stránku služby SharePoint aplikace nebo webovou část | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- user controls [SharePoint development in Visual Studio], adding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 98333049f711e9d28d7adb1ad0c17cfc8514e4ad
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120164"
---
# <a name="how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part"></a>Postupy: vytvoření uživatelského ovládacího prvku pro aplikace stránku nebo webovou část služby SharePoint
  Můžete také vytvářet vlastní uživatelské ovládací prvky, které poskytují vlastní funkce pro řešení služby SharePoint, a tyto funkce v rámci svého projektu znovu využívat. De webové části nebo do stránky aplikace lze zahrnout uživatelské ovládací prvky, přidat další ovládací prvky technologie ASP.NET, ovládací prvky služby SharePoint a definovat vlastnosti a metody pro ovládací prvek. Další informace o uživatelských ovládacích prvků najdete v tématu [vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md) a [uživatelské ovládací prvky a ovládací prvky serveru ve službě SharePoint](http://blogs.msdn.com/b/kaevans/archive/2011/04/28/user-controls-and-server-controls-in-sharepoint.aspx).  
  
### <a name="to-create-a-user-control-for-sharepoint"></a>Vytvoření uživatelského ovládacího prvku služby SharePoint.  
  
1.  V aplikaci Visual Studio otevřete nebo vytvořte projekt služby SharePoint.  
  
     V tématu [SharePoint projekt a projekt šablon položek](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  V **Průzkumníku**, vyberte uzel projektu.  
  
3.  Na řádku nabídek zvolte **projektu** > **přidat novou položku**.  
  
     **Přidat novou položku** otevře se dialogové okno.  
  
4.  V **nainstalovaná** podokně, vyberte **Office/SharePoint** uzlu.  
  
5.  V seznamu šablon služby SharePoint, zvolte **uživatelský ovládací prvek (pouze řešení farmy)**.  
  
    > [!NOTE]  
    >  Uživatelské ovládací prvky fungují pouze pro řešení farmy.  
  
6.  V **název** pole, zadejte název pro uživatelský ovládací prvek a potom zvolte **přidat** tlačítko.  
  
     Aplikace Visual Studio přidá do projektu několik složek a souborů. Další informace o těchto souborech najdete v tématu [vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
     Ve výchozím souboru uživatelského ovládacího prvku se zobrazí v **zdroj** zobrazení návrháře Visual Web Developer. V tomto zobrazení lze upravit značku XML ovládacího prvku. Můžete přepnout **návrhu** zobrazit, pokud chcete navrhnout ovládacího prvku vizuálně přetažením ovládacích prvků z **sada nástrojů**. V tématu [návrhu, Designer webových stránek](http://msdn.microsoft.com/en-us/d8f2270a-357d-40a4-9b39-1a3f2366216d).  
  
7.  Pokud chcete zpracovávat události, ke kterým došlo v ovládacím prvku, přidejte kód do souboru kódu uživatelského ovládacího prvku.  
  
     Tento soubor se zobrazí v **Průzkumníku řešení** v souboru uživatelského ovládacího prvku a má *.cs* nebo *VB* rozšíření, v závislosti na jazyk projektu.  
  
## <a name="see-also"></a>Viz také:
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)  
  
