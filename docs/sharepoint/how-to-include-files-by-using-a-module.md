---
title: 'Postupy: Zahrnutí souborů pomocí modulu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5813a6f89062bf53f7f8c0b57b4ed3a8ef9c4edf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62813641"
---
# <a name="how-to-include-files-by-using-a-module"></a>Postupy: Zahrnutí souborů pomocí modulu
  *Moduly* (Nezaměňovat s [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] moduly) jsou kontejnery, které vám umožňují nasazovat Image, textové soubory nebo soubory, jako jsou hlavní stránky ASPX do Sharepointu.

 Můžete k nasazení souboru do knihovny dokumentů nebo jako normální soubor (například default.aspx) mimo knihovnu dokumentů. Chcete-li přidat soubor do knihovny dokumentů, zadejte `Type="GhostableInLibrary"` jako atribut v **souboru** elementu. Toto nastavení nastaví Sharepointu vytvořit položku seznamu pro váš soubor při přidání do knihovny. Pokud chcete nasadit soubor mimo knihovnu dokumentů, zadejte `Type="Ghostable"` nebo jednoduše vynechejte **typ** atribut.

## <a name="add-a-module-to-a-sharepoint-solution"></a>Přidat modul do řešení služby SharePoint

#### <a name="to-add-a-module"></a>Přidat modul

1. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevření nebo vytvoření projektu služby SharePoint.

     Další informace najdete v tématu [SharePoint šablony položek projektu a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. V **Průzkumníka řešení**, zvolte uzel projektu a pak na panelu nabídek zvolte **projektu** > **přidat novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

3. V seznamu šablon služby SharePoint, zvolte **modulu** šablony a klikněte na tlačítko **přidat** tlačítko.

     Tento krok vytvoří uzel v projektu s názvem modulu 1.

4. V části Module1, odstranit *ukázka.txt* souboru.

     Ukázka.txt je součástí všechny nové moduly například účely a není potřeba. (Všimněte si, že soubor odstranit také odebere jeho položku z modulu *Elements.xml* souboru.)

5. Pokud chcete, aby vaše soubory k nasazení do struktury konkrétní složky v Sharepointu, vytváření těchto složek v rámci modulu 1 v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kliknutím na možnost Module1 uzel a potom na panelu nabídek, výběrem **projektu**, **nový Složka**.

6. Vyberte složku, ve které chcete přidat soubor a pak na panelu nabídek zvolte **projektu**, **přidat existující položku**.

7. Vyberte jeden nebo více souborů, které chcete nasadit do Sharepointu a klikněte na tlačítko **přidat** tlačítko.

     Při přidání souboru do projektu položku, se automaticky přidá do souboru Elements.xml modulu. Při nasazení projektu soubory se zkopírují na server SharePoint, vzhledem k projektu kořenový adresář, který je určený **souboru** elementu **Url** atribut, například `Url="Module1/New Folder/SomeFile.doc`. Pokud chcete změnit umístění nasazení pro soubor, buď ji přesunout do jiné složky v **Průzkumníka řešení** nebo změnit jeho **Url** nastavení.

8. Všechny soubory, které chcete zobrazit v knihovně dokumentů, připojte `Type="GhostableInLibrary"` atribut jejich záznamu ve *Elements.xml*. Například

    ```xml
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />
    ```

9. Nasazení projektu.

     Zkopírujte soubory do určitých umístění ve službě SharePoint.

## <a name="see-also"></a>Viz také:
- [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
