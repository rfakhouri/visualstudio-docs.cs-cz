---
title: Rozšíření nástrojů SharePoint v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio, extending tools
- extensibility [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extending tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7d5ad6f27574fcb7bd8a859bcd21ac65e159596e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="extending-the-sharepoint-tools-in-visual-studio"></a>Rozšíření nástrojů SharePoint v aplikaci Visual Studio
  Nástroje služby SharePoint v sadě Visual Studio splňovat požadavky na mnoho scénářů vývoje aplikace. Však může zjišťovat případech, kde neposkytují funkce, které vy nebo jiní vývojáři vyžadují. V těchto případech můžete rozšířit nástroje služby SharePoint pro vytvoření funkce, které potřebujete.  
  
## <a name="how-to-extend-the-sharepoint-tools"></a>Postup rozšíření nástrojů SharePoint  
 Můžete rozšíření systému projektu služby SharePoint a **připojení služby SharePoint** uzlu **Průzkumníka serveru** okno.  
  
### <a name="extending-the-sharepoint-project-system"></a>Rozšíření systému projektu služby SharePoint  
 Visual Studio obsahuje sadu šablony projektů a šablon položek, které můžete použít k vytvoření řešení služby SharePoint. Například jsou šablony pro přijímače událostí, seznam definic, pracovní postupy a webové části. Můžete však také definovat vlastních typů položek projektu služby SharePoint pro vytvoření součásti služby SharePoint, jako je například pole nebo vlastní akce. Můžete také vytvořit rozšíření pro typů položek projektu služby SharePoint, které již jsou nainstalovány v sadě Visual Studio a rozšíření pro projekty SharePoint můžete vytvořit.  
  
 Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).  
  
### <a name="extending-the-sharepoint-connections-node-in-server-explorer"></a>Rozšíření uzlu připojení služby SharePoint v průzkumníku serveru  
 V sadě Visual Studio, můžete použít **připojení služby SharePoint** uzlu**Průzkumníka serveru** pro zobrazení mnoha součástí jedné nebo více místních webů služby SharePoint v hierarchickém stromovém zobrazení. Můžete také rozšířit **připojení služby SharePoint** uzlu následujícími způsoby:  
  
-   Přidáním vlastních uzlů. To je užitečné, pokud chcete zobrazit součásti webů služby SharePoint, které nejsou ve výchozím nastavení zobrazí.  
  
-   Pomocí rozšíření existujících uzlů. Například můžete přidat nové podřízený uzel do existujícího uzlu, nebo můžete přidat položky místní nabídky do uzlu a provádět úlohy, když vývojář klikne na položku nabídky.  
  
 Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).  
  
## <a name="development-computer-requirements"></a>Požadavky na vývoj pro počítač  
 Vytvoření rozšíření pro nástroje služby SharePoint, vývojovém počítači, musí splňovat stejné požadavky na vytváření řešení služby SharePoint v sadě Visual Studio. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
 Doporučujeme také nainstalovat [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Sada SDK zahrnuje šablony projektů a nástroje, které můžete použít k rozšíření sady Visual Studio. Sada SDK zahrnuje zejména šablona projektu, které můžete snadno vytvořit balíček rozšíření Visual Studio (VSIX). VSIX balíčky jsou upřednostňovaný způsob, jak nasadit rozšíření Visual Studia v sadě Visual Studio. Všechna rozšíření nástrojů služby SharePoint se musí nasadit pomocí balíčků VSIX. Všechny postupy v této dokumentaci se předpokládá, že máte [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)] nainstalována.  
  
 Chcete-li nainstalovat sadu Visual Studio SDK, přečtěte si téma [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md). Další informace o rozšíření Visual Studia, najdete v části [zahajuje se vyvíjet rozšíření Visual Studia](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled modelu programování SharePoint rozšíření nástrojů](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Programování konceptů a funkcí pro rozšíření nástrojů SharePoint](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [Referenční dokumentace &#40;rozšíření nástrojů SharePoint&#41;](../sharepoint/reference-sharepoint-tools-extensibility.md)   
 [Ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)   
 [Nasazování rozšíření pro nástroje služby SharePoint v aplikaci Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  