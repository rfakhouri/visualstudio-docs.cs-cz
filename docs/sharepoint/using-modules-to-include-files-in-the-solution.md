---
title: Vložené soubory v řešení pomocí modulů | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deployment modules
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f9389e5928c74e5ee60bee90b375671777f1b807
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="using-modules-to-include-files-in-the-solution"></a>Vložení souborů do řešení pomocí modulů
  Může nastat situace, kdy můžete chtít nasadit soubory na server SharePoint bez ohledu na jejich typ souboru, jako je například nové stránky předlohy. Chcete-li to provést, můžete použít *moduly* (Nezaměňovat s [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] code moduly). Moduly jsou kontejnery pro soubory v řešení služby SharePoint. Po nasazení řešení se soubory v modulu se zkopírují do zadané složky na serveru SharePoint.  
  
## <a name="module-items-and-elements"></a>Modul položky a elementy  
 Vytvořit modul, přidejte ji do projektu ji v výběrem **přidat novou položku** dialogové okno. Upravte svůj soubor Elements.xml do zahrnout názvy souborů, které chcete nasadit, kde se nacházejí v systému, a kde mají být zkopírovány na server služby SharePoint.  
  
 Tady je příklad souboru Elements.xml pro modul:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
    <Module Name="Module1">  
        <File Path="Module1\Sample.txt" Url="Module1/Sample.txt" />  
    </Module>  
</Elements>  
  
```  
  
 Nově vytvořený moduly obsahují následující výchozí soubory:  
  
|Název souboru|Popis|  
|---------------|-----------------|  
|Elements.XML|Soubor definice modulu.|  
|Ukázka.txt|Zástupný soubor, který slouží jako příklad souboru v modulu.|  
  
 Soubor Elements.xml obsahuje následující prvky:  
  
|Název elementu|Popis|  
|------------------|-----------------|  
|Elementy|Obsahuje všechny prvky definované v modulu.|  
|Modul|Element modulu má jeden atribut, *název*, který určuje název modulu ve formátu `<Module Name="Module1">`.<br /><br /> Všimněte si, že pokud změníte název měněného modulu (nebo její *název složky* vlastnost), je nutné ručně aktualizovat název v elementu modulu.<br /><br /> Pokud podadresáři pro soubory, které zadáte v elementu modulu [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS) automaticky vytvoří odpovídající adresářovou strukturu pro ně.|  
|Soubor|Element souboru má dva parametry *cesta* a *Url*.<br /><br /> -Path: Název a umístění souboru v řešení služby SharePoint. Formát je, `Path="Module1\Sample.txt"`.<br /><br /> -Adresa Url: Umístění, kde bude soubor nasazen na serveru SharePoint. Formát je, `Url="Module1/Sample.txt"`.<br /><br /> -Type: Volitelný atribut, který má dvě nastavení: *GhostableInLibrary* a *Ghostable*. Formát je, `Type="GhostableInLibrary"`. Určení *GhostableInLibrary* znamená přidá soubor do knihovny dokumentů ve službě SharePoint společně s položku seznamu, který může doprovázet soubor při jejím přidání do knihovny. Určení *Ghostable* způsobí, že soubor, který se má přidat do služby SharePoint mimo knihovnu dokumentů.|  
  
 Každý soubor, který chcete nasadit vyžaduje samostatné `<File>` element položku v Elements.xml.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: zahrnutí souborů pomocí modulu](../sharepoint/how-to-include-files-by-using-a-module.md)   
 [postupy: zřídit soubor](http://go.microsoft.com/fwlink/?LinkID=144271)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  