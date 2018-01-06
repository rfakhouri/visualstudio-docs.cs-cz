---
title: "Postupy: vystavení kódu do VBA v projektu jazyka Visual C# | Microsoft Docs"
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
helpviewer_keywords:
- Visual C# [Office development in Visual Studio], exposing code to VBA
- VBA [Office development in Visual Studio], exposing code in document-level customizations
- document-level customizations [Office development in Visual Studio], exposing code
- exposing code to VBA
ms.assetid: 56d5894b-4823-42f4-8c7e-d8739b859c52
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 671618479b1be55fcf08d93b2a398c27348b9878
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-expose-code-to-vba-in-a-visual-c-project"></a>Postupy: Vystavení kódu v projektu jazyka Visual C# pro jazyk VBA
  Můžete vystavení kódu v jazyce Visual C# projektu do jazyka Visual Basic pro aplikace (VBA) kód, pokud chcete, aby dva typy kódu dojít ke vzájemné interakci.  
  
 Proces Visual C# se liší od proces jazyka Visual Basic. Další informace najdete v tématu [postupy: vystavení kódu do VBA v projektu jazyka Visual Basic](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="exposing-code-in-a-visual-c-project"></a>Vystavení kódu v projektu jazyka Visual C#  
 Pokud chcete povolit VBA kód pro volání kódu v projektu jazyka Visual C#, změnit kód tak, aby byl viditelný pro COM a nastavte **ReferenceAssemblyFromVbaProject** vlastnost, která má **True** v návrháři.  
  
 Návod, který ukazuje, jak volat metodu z jazyka VBA v projektu jazyka Visual C#, najdete v části [návod: volání kódu z jazyka VBA v Visual C &#35; Projekt](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md).  
  
#### <a name="to-expose-code-in-a-visual-c-project-to-vba"></a>K vystavení kódu v projektu jazyka Visual C# pro jazyk VBA  
  
1.  Otevřete nebo vytvořte projekt na úrovni dokumentu, který je založený na dokument aplikace Word, sešit aplikace Excel nebo Excel šablony, která podporuje makra, který již obsahuje VBA kód.  
  
     Další informace o formátech souborů dokumentu, které podporují makra najdete v tématu [kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
    > [!NOTE]  
    >  Tuto funkci nelze použít v šabloně projekty aplikace Word.  
  
2.  Zajistěte, aby je spustit bez výzvy pro uživatele, povolit makra VBA kód v dokumentu. VBA kód pro spuštění přidáním umístění Microsoft Office project do seznamu důvěryhodných lokalit v nastavení Centrum zabezpečení pro Word či Excel můžete důvěřovat.  
  
3.  Přidat člena, který chcete zpřístupnit pro jazyk VBA veřejnou třídu ve vašem projektu a deklarovat nového člena jako **veřejné**.  
  
4.  Použít následující <xref:System.Runtime.InteropServices.ComVisibleAttribute> a <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atributy pro třídu, která jsou vystavení pro jazyk VBA. Tyto atributy zviditelnit třídu do modelu COM, ale bez generování třídy rozhraní.  
  
    ```csharp  
    [System.Runtime.InteropServices.ComVisible(true)]  
    [System.Runtime.InteropServices.ClassInterface(  
        System.Runtime.InteropServices.ClassInterfaceType.None)]  
    ```  
  
5.  Přepsání **GetAutomationObject** metoda třídy položky hostitele ve vašem projektu a vrátit instanci třídy, která jsou vystavení pro jazyk VBA:  
  
    -   Pokud jsou vystavení třídu položky hostitele pro jazyk VBA, mají přednost před **GetAutomationObject** metodu, která patří do této třídy a vrátí aktuální instance třídy.  
  
        ```csharp  
        protected override object GetAutomationObject()  
        {  
            return this;  
        }  
        ```  
  
    -   Pokud jsou vystavení třídu, která není položka hostitele pro jazyk VBA, mají přednost před **GetAutomationObject** metoda libovolného hostitele položky ve vašem projektu a vrátit instanci třídy jiný hostitelská položka. Například následující kód předpokládá, že vystavujete třídy s názvem `DocumentUtilities` pro jazyk VBA.  
  
        ```csharp  
        protected override object GetAutomationObject()  
        {  
            return new DocumentUtilities();  
        }  
        ```  
  
     Další informace o hostitelských položkách najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
6.  Extrahování rozhraní ze třídy, která jsou vystavení pro jazyk VBA. V **extrahování rozhraní** dialogovém okně vyberte veřejné členy, které chcete zahrnout do deklarace rozhraní. Další informace najdete v tématu [extrahování rozhraní refaktoring &#40; C &#35; &#41; ](/visualstudio/csharp-ide/extract-interface-refactoring-csharp).  
  
7.  Přidat **veřejné** – klíčové slovo deklaraci rozhraní.  
  
8.  Zpřístupněte rozhraní COM přidáním následující <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut rozhraní.  
  
    ```csharp  
    [System.Runtime.InteropServices.ComVisible(true)]  
    ```  
  
9. Otevřít dokument (pro aplikaci Word) nebo listu (pro aplikaci Excel) v Návrháři v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
10. V **vlastnosti** vyberte **ReferenceAssemblyFromVbaProject** vlastnost a změňte hodnotu na **True**.  
  
    > [!NOTE]  
    >  Pokud sešit nebo dokument už neobsahuje VBA kód nebo pokud VBA kód v dokumentu není důvěryhodný pro spuštění, zobrazí se chybová zpráva při nastavení **ReferenceAssemblyFromVbaProject** vlastnost **True**. Je to proto, že Visual Studio nelze změnit na projekt VBA v dokumentu v této situaci.  
  
11. Klikněte na tlačítko **OK** zprávy, která se zobrazí. Tato zpráva upozorní, že pokud přidáte VBA pro vytváření kódu v sešitu nebo dokumentu při spuštění projektu z [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA kód budou ztraceny při příštím sestavte projekt. Je to proto, že dokument v sestavení výstupu složky se přepíše pokaždé, když vytvoříte projekt.  
  
     V tomto okamžiku Visual Studio nastaví projekt tak, aby projekt VBA můžete volat do sestavení. Visual Studio také přidá metodu s názvem `GetManagedClass` do projektu VBA pro vytváření. Tuto metodu lze volat z libovolného místa v projektu VBA pro vytváření pro třídu, která vystavený pro jazyk VBA přístup.  
  
12. Sestavte projekt.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Návod: Volání kódu z jazyka VBA v Visual C &#35; Projekt](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)   
 [Postupy: Vystavení kódu v projektu jazyka Visual Basic pro jazyk VBA](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)  
  
  