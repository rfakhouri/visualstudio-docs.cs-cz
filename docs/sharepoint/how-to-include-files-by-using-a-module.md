---
title: "Postupy: zahrnutí souborů pomocí modulu | Microsoft Docs"
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
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: ebefc0420eba48fdc53e68482a96a575111e536f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-include-files-by-using-a-module"></a>Postupy: Zahrnutí souborů pomocí modulu
  *Moduly* (Nezaměňovat s [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] moduly) jsou kontejnery, které vám umožní nasadit soubory, jako jsou hlavní stránky ASPX, textové soubory nebo bitové kopie do služby SharePoint.  
  
 Můžete nasazovat soubor do knihovny dokumentů nebo jako normální soubor (například default.aspx) mimo knihovnu dokumentů. Chcete-li přidat soubor do knihovny dokumentů, zadejte `Type="GhostableInLibrary"` jako atribut v **souboru** elementu. Toto nastavení dá pokyn služby SharePoint k vytvoření položky seznamu můžete využívat souboru při jejím přidání do knihovny. K nasazení souboru mimo knihovnu dokumentů, buď zadejte `Type="Ghostable"` nebo právě vynechejte **typ** atribut.  
  
## <a name="adding-a-module-to-a-sharepoint-solution"></a>Přidáním modulu do řešení služby SharePoint  
  
#### <a name="to-add-a-module"></a>Chcete-li přidat modul  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete nebo vytvoření projektu služby SharePoint.  
  
     Další informace najdete v tématu [projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
     **Přidat novou položku** otevře se dialogové okno.  
  
3.  V seznamu šablon služby SharePoint, vyberte **modulu** šablony a potom zvolte **přidat** tlačítko.  
  
     Tento krok vytvoří uzel v projektu s názvem modul 1.  
  
4.  V části modul 1 odstraňte soubor ukázka.txt.  
  
     Ukázka.txt je zahrnuta ve všech modulech nové například účely a není potřeba. (Všimněte si, že soubor odstranit také odebere jeho položku ze souboru Elements.xml modulu.)  
  
5.  Pokud chcete, aby vaše soubory nasadit do konkrétní složky struktury ve službě SharePoint, vytvořte tyto složky pod modul 1 v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] výběrem uzlu modul 1 a potom v nabídce panelu Výběr **projektu**, **nový Složka**.  
  
6.  Vyberte složku, ve které chcete přidat soubor a potom na řádku nabídek zvolte **projektu**, **přidat existující položku**.  
  
7.  Vyberte jeden nebo více souborů, které chcete nasadit do služby SharePoint a pak vyberte **přidat** tlačítko.  
  
     Když přidáte do projektu soubor, položku pro něj se automaticky přidá do souboru Elements.xml modulu. Při nasazení projektu, soubory se zkopírují na server služby SharePoint, vzhledem k projektu kořenový adresář, který je určený **soubor** elementu **Url** atributů, jako například `Url="Module1/New Folder/SomeFile.doc`. Pokud chcete změnit umístění nasazení pro soubor, buď ji přesunout do jiné složky v **Průzkumníku řešení** nebo změnit jeho **Url** nastavení.  
  
8.  Pro všechny soubory, které se má zobrazit v knihovně dokumentů, připojte `Type="GhostableInLibrary"` atribut jejich položku v Elements.xml. Například  
  
    ```  
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />  
    ```  
  
9. Nasazení projektu.  
  
     Zkopírujte soubory do určitých umístění ve službě SharePoint.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  