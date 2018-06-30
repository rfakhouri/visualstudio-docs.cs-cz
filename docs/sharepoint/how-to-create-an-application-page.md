---
title: 'Postupy: vytvoření stránky aplikace | Microsoft Docs'
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
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eefbb12584cdff2bb32b9d4406c916969ec435c4
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120161"
---
# <a name="how-to-create-an-application-page"></a>Postupy: vytvoření stránky aplikace
  Můžete vytvořit webovou stránku ASP.NET pro jeden nebo více webů služby SharePoint. Ve službě SharePoint se nazývají tyto stránek stránky aplikací. Na rozdíl od stránka stránky aplikace obsahuje kód, který se spouští za stránky. Další informace najdete v tématu [vytvoření stránky aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
### <a name="to-create-an-application-page"></a>Vytvoření stránky aplikace  
  
1.  V aplikaci Visual Studio otevřete nebo vytvořte projekt služby SharePoint.  
  
     Další informace najdete v tématu [SharePoint projekt a projekt šablon položek](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  V **Průzkumníku**, vyberte uzel projektu.  
  
3.  Na řádku nabídek zvolte **projektu** > **přidat novou položku**.  
  
4.  V **přidat novou položku** dialogové okno, rozbalte seznam **SharePoint** uzel a potom zvolte **2010** položky.  
  
5.  V seznamu šablon služby SharePoint, zvolte **stránky aplikace**.  
  
6.  V **název** pole, zadejte název pro stránku aplikace a pak zvolte **přidat** tlačítko.  
  
     Aplikace Visual Studio přidá do projektu několik složek a souborů. Další informace o těchto souborech najdete v tématu [vytvoření stránky aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
     V **zdroj** návrháře Visual Web Developer souboru stránky ASP.NET se zobrazí. Stránky můžete navrhnout přidáním ovládacích prvků z **sada nástrojů** a jejich umístění na zástupné symboly obsahu. Další informace najdete v tématu [zobrazení zdroje, Návrhář webové stránky](http://msdn.microsoft.com/en-us/5911396b-fe51-4150-9ff1-b085f812862f).  
  
7.  Pokud chcete pro zpracování události ovládacího prvku, přidáte kód do souboru kódu pro stránku aplikace.  
  
     K souboru kódu se zobrazí v případě, že rozbalte uzel souboru stránky ASP.NET a má *.cs* nebo *VB* rozšíření, v závislosti na jazyk projektu. Příklad začátku do konce Vytvoření stránky aplikace naleznete v části [návod: vytvoření stránky aplikace služby SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md).  
  
## <a name="see-also"></a>Viz také:
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Návod: Vytvoření stránky aplikace služby SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
