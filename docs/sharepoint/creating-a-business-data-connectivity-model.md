---
title: Vytvoření modelu připojení obchodních dat | Microsoft Docs
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
- Business Data Connectivity service [SharePoint development in Visual Studio], model
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- SharePoint development in Visual Studio, Business Data Connectivity service
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f823c8c67750dec31c6c2b534ecc7500e20defaf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-business-data-connectivity-model"></a>Vytvoření modelu připojení obchodních dat
  Můžete vytvořit model Business Data Connectivity (BDC) nebo si přizpůsobit existujícího modelu služby BDC pomocí sady Visual Studio. Každý projekt SharePoint může obsahovat jenom jeden model. Další informace najdete v tématu [integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md).  
  
## <a name="creating-a-new-model"></a>Vytvoření nového modelu  
 Chcete-li vytvořit nový model, vytvořte **modelu připojení obchodních dat** projektu nebo přidejte **modelu připojení obchodních dat** položkou **prázdný projektu služby SharePoint**.  
  
> [!NOTE]  
>  Musíte mít [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] v počítači nainstalována.  
  
 Visual Studio přidá do složky do projektu. Tato složka obsahuje název, který zadáte pro **modelu připojení obchodních dat** položky v **přidat novou položku** dialogové okno. Pokud vytvoříte novou **modelu připojení obchodních dat** projektu sady Visual Studio názvy složce **BdcModel1**.  
  
 Visual Studio. přidá následující soubory do nové složky:  
  
|Soubor|Popis|  
|----------|-----------------|  
|Soubor definice modelu|Obsahuje kód XML, který definuje entity, metod, systémové objekty obchodnímu systému (LOB) a další metadata, která popisuje model.<br /><br /> Změna metadat v tomto souboru pomocí návrháře BDC **Průzkumník modelu BDC**, **podrobnosti o metodě BDC** okně a **vlastnosti** okno.|  
|Entity souboru kódu služby|Obsahuje metody, které získat, aktualizovat a odstranit instance entity výchozí.|  
  
 K definování vlastností entity, upravte soubor kód entity. Další informace najdete v tématu [postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
 Získat, aktualizovat a odstraňovat instance entity, přidáte kód do souboru kódu služby entity. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Při kompilaci projekt Visual Studio vytvoří sestavení. Ujistěte se, nepřidávejte jiných položek pro projekt, který přidávání kódu do sestavení projektu (například: **sekvenční pracovní postup** položky nebo **webovou část** položky). Kód pro tuto položku se nespustí, když nasadíte řešení, protože balíček řešení nekopíruje sestavení do globální mezipaměti sestavení.  Balíček řešení nasadí do databáze služby BDC ve službě SharePoint pouze sestavení.  
  
> [!NOTE]  
>  Při ladění projektu sady Visual Studio zkopíruje sestavení do obou umístění v místním počítači.  
  
## <a name="adding-an-existing-model"></a>Přidání existujícího modelu  
 Můžete importovat model, který byl vytvořen pomocí jiných nástrojů, například SharePoint Designer. Můžete zvolit importovat existující model do projektu v následujících situacích:  
  
-   Chcete-li přizpůsobit model, který je už nasazená do farmy serverů SharePoint.  
  
-   Balíček a nasazení existujícího modelu do více serverové farmy služby SharePoint.  
  
 V obou případech systémům LOB definované v modelu, který importujete, nejsou nijak ovlivněny a budou nadále fungovat podle očekávání. K přidání existujícího modelu do projektu služby SharePoint, použijte Visual Studio **přidat existující položku** dialogové okno. Další informace najdete v tématu [postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md).  
  
 Systému LOB sestavení rozhraní .NET Framework typ importované modelu můžete přidat výběrem možnosti v **sestavení .NET přidat LobSystem**. To umožňuje psát vlastní kód a použijte k definování metadata pro importovaný model návrháře.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)|Ukazuje, jak vytvořit nový model BDC.|  
|[Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)|Ukazuje, jak importovat existující model do projektu služby SharePoint.|  
|[Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)|Popisuje, jak poskytnout řetězce, které jsou slučovány metadat modelu, pokud model je spotřebovávají webové části nebo webové stránky.|  
|[Postupy: Zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)|Ukazuje, jak k zahrnutí vlastního sestavení ve funkci.|  
  
  