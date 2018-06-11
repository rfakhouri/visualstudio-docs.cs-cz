---
title: 'Postupy: vystavení kódu do VBA v projektu jazyka Visual Basic'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], exposing code in document-level customizations
- document-level customizations [Office development in Visual Studio], exposing code
- Visual Basic [Office development in Visual Studio], exposing code to VBA
- exposing code to VBA
- host items [Office development in Visual Studio], exposing code to VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8a979d62c8320d57c3243e4d60ef93ee56eb06cf
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256094"
---
# <a name="how-to-expose-code-to-vba-in-a-visual-basic-project"></a>Postupy: vystavení kódu do VBA v projektu jazyka Visual Basic
  Můžete vystavení kódu v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projektu do jazyka Visual Basic pro aplikace (VBA) kód, pokud chcete, aby dva typy kódu dojít ke vzájemné interakci.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Visual Basic proces se liší od proces Visual C#. Další informace najdete v tématu [postupy: vystavení kódu do VBA v Visual C&#35; projektu](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md).  
  
 Proces se liší pro kód ve třídě položky hostitele, než je pro kód ve ostatní třídy:  
  
-   [Vystavení kódu v třídě položky hostitele](#HostItemCode)  
  
-   [Vystavení kódu, který není v třídě položky hostitele](#NonHostItem)  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak VSTO I: volání kódu z jazyka VBA?](http://go.microsoft.com/fwlink/?LinkId=136757).  
  
##  <a name="HostItemCode"></a> Vystavení kódu v třídě položky hostitele  
 Chcete-li povolit VBA kód volat kód jazyka Visual Basic v třídě položky hostitele, nastavte **EnableVbaCallers** vlastnosti položky hostitele k **True**.  
  
 Návod, jak vystavit metodu, třídu položky hostitele a poté ji volat z jazyka VBA najdete v tématu [návod: volání kódu z jazyka VBA v projektu jazyka Visual Basic](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md). Další informace o hostitelských položkách najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
#### <a name="to-expose-code-in-a-host-item-to-vba"></a>K vystavení kódu v položce hostitele pro jazyk VBA  
  
1.  Otevřít nebo vytvořit úrovni dokumentu [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projektu, který je založený na dokument aplikace Word, sešit aplikace Excel nebo Excel šablony, která podporuje makra, který již obsahuje VBA kód.  
  
     Další informace o formátech souborů dokumentu, které podporují makra najdete v tématu [kombinovat VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Tuto funkci nelze použít v šabloně projekty aplikace Word.  
  
2.  Zajistěte, aby je spustit bez výzvy pro uživatele, povolit makra VBA kód v dokumentu. VBA kód pro spuštění přidáním umístění Microsoft Office project do seznamu důvěryhodných lokalit v nastavení Centrum zabezpečení pro Word či Excel můžete důvěřovat.  
  
3.  Přidání vlastností, metoda nebo událostí, které chcete zpřístupnit pro jazyk VBA na jednu z tříd položek hostitele ve vašem projektu a deklarovat nového člena jako **veřejné**. Název třídy, závisí na aplikaci:  
  
    -   V textovém projektu, třída položky hostitele názvem `ThisDocument` ve výchozím nastavení.  
  
    -   V projektu aplikace Excel, jsou pojmenované tříd položek hostitele `ThisWorkbook`, `Sheet1`, `Sheet2`, a `Sheet3` ve výchozím nastavení.  
  
4.  Nastavte **EnableVbaCallers** vlastnost pro hostitelskou položku k **True**. Tato vlastnost je k dispozici v **vlastnosti** okno při hostitelská položka je otevřený v návrháři.  
  
     Po nastavení této vlastnosti, Visual Studio automaticky nastaví **ReferenceAssemblyFromVbaProject** vlastnost **True**.  
  
    > [!NOTE]  
    >  Pokud sešit nebo dokument už neobsahuje VBA kód, nebo pokud VBA kód v dokumentu není důvěryhodný pro spuštění, zobrazí se chybová zpráva při nastavení **EnableVbaCallers** vlastnost **True**. Je to proto, že Visual Studio nelze změnit na projekt VBA v dokumentu v této situaci.  
  
5.  Klikněte na tlačítko **OK** zprávy, která se zobrazí. Tato zpráva upozorní, že pokud přidáte VBA kód do sešitu nebo dokumentu při používáte projekt z [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kód budou ztraceny při příštím sestavte projekt. Je to proto, že dokument v zadané výstupní složce sestavení se přepíše pokaždé, když vytvoříte projekt.  
  
     V tomto okamžiku Visual Studio nastaví projekt tak, aby projekt VBA můžete volat do sestavení. Visual Studio také přidá vlastnost s názvem `CallVSTOAssembly` k `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2`, nebo `Sheet3` modulu v projektu VBA pro vytváření. Tato vlastnost slouží pro přístup k veřejné členy třídy, která vystavený pro jazyk VBA.  
  
6.  Sestavte projekt.  
  
##  <a name="NonHostItem"></a> Vystavení kódu, který není v třídě položky hostitele  
 Povolit VBA kód volat kód jazyka Visual Basic, který není v třídě položky hostitele, upravte kód tak, aby byl viditelný pro jazyk VBA.  
  
### <a name="to-expose-code-that-is-not-in-a-host-item-class-to-vba"></a>Aby se zveřejnily kód, který není v třídě položky hostitele pro jazyk VBA  
  
1.  Otevřít nebo vytvořit úrovni dokumentu [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projektu, který je založený na dokument aplikace Word, sešit aplikace Excel nebo Excel šablony, která podporuje makra, který již obsahuje VBA kód.  
  
     Další informace o formátech souborů dokumentu, které podporují makra najdete v tématu [kombinovat VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Tuto funkci nelze použít v šabloně projekty aplikace Word.  
  
2.  Zajistěte, aby je spustit bez výzvy pro uživatele, povolit makra VBA kód v dokumentu. VBA kód pro spuštění přidáním umístění Microsoft Office project do seznamu důvěryhodných lokalit v nastavení Centrum zabezpečení pro Word či Excel můžete důvěřovat.  
  
3.  Přidat člena, který chcete zpřístupnit pro jazyk VBA veřejnou třídu ve vašem projektu a deklarovat nového člena jako **veřejné**.  
  
4.  Použít následující <xref:System.Runtime.InteropServices.ComVisibleAttribute> a <xref:Microsoft.VisualBasic.ComClassAttribute> atributy pro třídu, která jsou vystavení pro jazyk VBA. Tyto atributy zviditelnit třídy pro jazyk VBA.  
  
    ```vb  
    <Microsoft.VisualBasic.ComClass()> _  
    <System.Runtime.InteropServices.ComVisibleAttribute(True)> _  
    ```  
  
5.  Přepsání **GetAutomationObject** metoda třídy položky hostitele ve vašem projektu a vrátit instanci třídy, která jsou vystavení pro jazyk VBA. Následující příklad kódu předpokládá, že vystavujete třídy s názvem `DocumentUtilities` pro jazyk VBA.  
  
    ```vb  
    Protected Overrides Function GetAutomationObject() As Object  
        Return New DocumentUtilities()  
    End Function  
    ```  
  
6.  Otevřít dokument (pro aplikaci Word) nebo Návrhář listu (pro aplikaci Excel) v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
7.  V **vlastnosti** vyberte **ReferenceAssemblyFromVbaProject** vlastnost a změňte hodnotu na **True**.  
  
    > [!NOTE]  
    >  Pokud sešit nebo dokument už neobsahuje VBA kód, nebo pokud VBA kód v dokumentu není důvěryhodný pro spuštění, zobrazí se chybová zpráva při nastavení **ReferenceAssemblyFromVbaProject** vlastnost **True** . Je to proto, že Visual Studio nelze změnit na projekt VBA v dokumentu v této situaci.  
  
8.  Klikněte na tlačítko **OK** zprávy, která se zobrazí. Tato zpráva upozorní, že pokud přidáte VBA kód do sešitu nebo dokumentu při používáte projekt z [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kód budou ztraceny při příštím sestavte projekt. Je to proto, že dokument v zadané výstupní složce sestavení se přepíše pokaždé, když vytvoříte projekt.  
  
     V tomto okamžiku Visual Studio nastaví projekt tak, aby projekt VBA můžete volat do sestavení. Visual Studio také přidá metodu s názvem `GetManagedClass` do projektu VBA pro vytváření. Tuto metodu lze volat z libovolného místa v projektu VBA pro vytváření pro třídu, která vystavený pro jazyk VBA přístup.  
  
9. Sestavte projekt.  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Návod: Volání kódu z jazyka VBA v projektu jazyka Visual Basic](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [Postupy: vystavení kódu do VBA v Visual C&#35; projektu](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)  
  
  