---
title: 'Postupy: Import stránky předlohy nebo motivu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6cac959fb4f9c52849e6e121943fd847deb923d0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63427404"
---
# <a name="how-to-import-a-master-page-or-theme"></a>Postupy: Import stránky předlohy nebo motivu
  Můžete zadat stránky na webu služby SharePoint jednotný vzhled vytvořením a použitím stránky předlohy a motivů. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] neposkytuje šablon pro tyto elementy, ale můžete vytvořit v aplikaci SharePoint Designer a importujte je do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [stavebních bloků: Stránky a uživatelské rozhraní](http://go.microsoft.com/fwlink/?LinkID=182095) na webu společnosti Microsoft.

### <a name="to-import-a-master-page-or-theme"></a>Chcete-li import stránky předlohy nebo motivu

1. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvořte nebo otevřete projekt služby SharePoint.

     Informace o tom, jak vytvořit projekt služby SharePoint, naleznete v tématu [SharePoint šablony položek projektu a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

3. V **přidat novou položku** dialogového okna rozbalte **SharePoint** uzel a klikněte na tlačítko **2010** uzlu.

4. V seznamu šablon služby SharePoint, zvolte **modulu** šablony a pak zadejte název modulu.

     Modul obsahuje soubory (například stránky předlohy nebo motivu souborů) pro nasazení do umístění, které zadáte v Sharepointu.

5. V modulu, odstraňte výchozí soubor, který se nazývá *ukázka.txt*.

6. Vyberte uzel modulu.

7. V panelu nabídky zvolte **projektu** > **přidat existující položku**a klikněte na tlačítko souboru hlavní stránky nebo motivu.

     Hlavní stránka soubory mají příponu .master a motivu soubory mají příponu .thmx.

8. Pokud jste přidali na stránku předlohy, změňte jeho **řešení konfliktů při nasazení** nastavení **automatické** ve vlastnostech modulu.

    > [!NOTE]
    > Pokud název hlavní stránky je stejná jako název existující stránky předlohy, která je označena jako výchozí stránky předlohy nebo vlastní stránky předlohy, může dojít k chybám. Informace o tom, jak tento problém vyřešit, najdete v části [názorný postup: Import vlastní stránky předlohy a stránky webu s obrázkem](../sharepoint/walkthrough-import-a-custom-master-page-and-site-page-with-an-image.md).

9. V modulu, otevřete *Elements.xml*.

     Je nutné aktualizovat *Elements.xml* souboru pro odkazování na stránky předlohy nebo motivu, kterou jste přidali.

10. Pro stránky předlohy nahraďte existující značky modulu následujícím kódem.

    ```xml
    <Module Name="[Module Name]" Url="_catalogs/masterpage">
        <File Path="[Module Name]\[Master Page Name].master"
          Url="[Master Page Name].master" Type="GhostableInLibrary" />
    </Module>
    ```

     Pro motiv nahraďte stávající kód modulu následující kód.

    ```xml
    <Module Name="[Module Name]" Url="_catalogs/theme"
        <File Path="[Module Name]\[Theme Name].thmx" Url="[Theme
          Name].thmx" Type="GhostableInLibrary" />
    </Module>
    ```

     Nezapomeňte nahradit hodnoty zástupných symbolů skutečné názvy modulu a stránky předlohy nebo motivu.

     Atribut `Type="GhostableInLibrary"` označuje, že je položka přidána do databáze obsahu a `Url` atribut modulu určuje, kam chcete soubor uložit v databázi obsahu služby SharePoint.

11. Postup změny oboru nasazení pro stránku předlohy **Průzkumníka řešení**, otevřete soubor funkce v Návrháři funkce a klikněte na tlačítko Nový rozsah nasazení z **oboru** seznamu.

     Hodnota **webové** znamená, že hlavní stránka se vztahuje pouze na webu, který je aktuálně zadaný v projektu. Hodnota **lokality** znamená, že hlavní stránka se vztahuje na aktuální kolekci webů, která zahrnuje všechny podřízené lokality a kořenového webu. Nemůžete použít jiné hodnoty.

    > [!NOTE]
    > Vzhledem k tomu, že motivy použít pouze na úrovni kolekce webů, doporučujeme, že nenastavíte oboru motiv na nic jiného než **lokality**. Pokud, motiv se používá v podřízeným webem, může dojít k chybám.

12. V panelu nabídky zvolte **sestavení** > **nasadit řešení**.

13. Pokud chcete ověřit, zda soubory se nasadily správně, otevřete web služby SharePoint, zvolte **Akce webu** nabídky, zvolte **nastavení webu** Apple a zvolte buď **stránky předlohy**  odkaz nebo **motivy** odkaz.

     Seznam stránky předlohy nebo motivy se zobrazí a obsahuje stránky předlohy nebo motivu, který jste importovali.

## <a name="see-also"></a>Viz také:
- [Stránky předlohy](http://go.microsoft.com/fwlink/?LinkId=184955)
- [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)
- [Vytváření stránek pro službu SharePoint](../sharepoint/creating-pages-for-sharepoint.md)
- [Vložení souborů do řešení pomocí modulů](../sharepoint/using-modules-to-include-files-in-the-solution.md)
