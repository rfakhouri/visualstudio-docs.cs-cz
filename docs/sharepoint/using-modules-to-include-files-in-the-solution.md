---
title: Vložení souborů do řešení pomocí modulů | Dokumentace Microsoftu
ms.date: 02/02/2017
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
ms.openlocfilehash: a9d8cf0da022c038c0e15e6b00f0bea0cdc3cef4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53921546"
---
# <a name="use-modules-to-include-files-in-the-solution"></a>Vložení souborů do řešení pomocí modulů
  Může nastat situace, kdy můžete chtít nasadit soubory k Sharepointovému serveru bez ohledu na jejich typ souboru, jako je například nové stránky předlohy. K tomuto účelu můžete použít *moduly* (Nezaměňovat s [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] moduly kódu). Moduly jsou kontejnery pro soubory v řešení služby SharePoint. Když se řešení nasadí, soubory v modulu se zkopírují do zadaných složek na serveru SharePoint.  
  
## <a name="module-items-and-elements"></a>Modul položky a prvky
 Jak vytvořit modul, přidejte ho do projektu, zvolte ji v **přidat novou položku** dialogové okno. Potom změňte jeho *Elements.xml* soubor zahrnout názvy souborů, které chcete nasadit, kde se nacházejí v systému a mají být zkopírovány na SharePoint server.  
  
 Tady je příklad *Elements.xml* souboru pro modul:  
  
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
|*Elements.XML*|Soubor definice modulu.|  
|*Ukázka.txt*|Zástupný soubor, který slouží jako příklad souboru v modulu.|  
  
 *Elements.xml* soubor obsahuje následující prvky:  
  
|Název elementu|Popis|  
|------------------|-----------------|  
|Elementy|Obsahuje všechny prvky definované v modulu.|  
|Modul|Element modulu obsahuje atribut jednu *název*, který určuje název modulu ve formátu `<Module Name="Module1">`.<br /><br /> Všimněte si, že pokud změníte název modulu (nebo jeho *název složky* vlastnost), je nutné ručně aktualizovat název v elementu modulu.<br /><br /> Pokud zadáte podadresář pro soubory v elementu modulu [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS) se automaticky vytvoří odpovídající adresářovou strukturu pro ně.|  
|Soubor|Prvek souboru má dva parametry *cesta* a *Url*.<br /><br /> -Path: Název a umístění souboru v řešení služby SharePoint. Formát je, `Path="Module1\Sample.txt"`.<br /><br /> – Adresa Url: Umístění, kam se soubor nasadí na SharePoint server. Formát je, `Url="Module1/Sample.txt"`.<br /><br /> -Typu: Volitelný atribut, který má dvě nastavení: *GhostableInLibrary* a *Ghostable*. Formát je, `Type="GhostableInLibrary"`. Určení *GhostableInLibrary* znamená, že soubor bude přidán do knihovny dokumentů sharepointu spolu s položku seznamu vyvíjený soubor, když se přidá do knihovny. Určení *Ghostable* způsobí, že soubor, který má být přidán do služby SharePoint mimo knihovnu dokumentů.|  
  
 Každý soubor, který chcete nasadit vyžaduje samostatnou `<File>` elementu vstupu v *Elements.xml*.  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Zahrnutí souborů pomocí modulu](../sharepoint/how-to-include-files-by-using-a-module.md)   
 [Jak: Zřízení souboru](http://go.microsoft.com/fwlink/?LinkID=144271)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
