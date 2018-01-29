---
title: "Postupy: určení událostí sestavení (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-build events
- events [Visual Studio], builds
- post-build events
- build events [Visual Studio]
- builds [Visual Studio], events
ms.assetid: 40dc83bf-a7c5-4a14-816a-fa0980b6e4c3
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0fe2ab7f174f71933d474aa4737dc713c6540492
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-specify-build-events-visual-basic"></a>Postupy: Určení událostí sestavení (Visual Basic)
Události sestavení v jazyce Visual Basic lze spustit skripty, makra nebo jiné akce jako součást procesu kompilace. Události před sestavením předcházet kompilaci. události po sestavení dojde po kompilaci.  
  
 Sestavení události jsou určené v **události sestavení** dialogové okno, k dispozici z **zkompilovat** stránky **Návrhář projektu**.  
  
> [!NOTE]
>  Visual Basic Express nepodporuje zadání událostí sestavení. Tato možnost je podporována pouze v plném produktu Visual Studio.  
  
## <a name="how-to-specify-pre-build-and-post-build-events"></a>Určení událostí před a po sestavení  
  
#### <a name="to-specify-a-build-event"></a>K určení událostí sestavení  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **zkompilovat** kartě.  
  
3.  Klikněte **události sestavení** tlačítko Otevřít **události sestavení** dialogové okno.  
  
4.  Zadejte argumenty příkazového řádku pro vaši akci před sestavením nebo po sestavení a pak klikněte na tlačítko **OK**.  
  
    > [!NOTE]
    >  Přidat `call` příkaz před příkazy všechny po sestavení, které spouštějí .bat soubory. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
    > [!NOTE]
    >  Pokud vaše události před sestavením nebo po sestavení úspěšně nedokončí, můžete ukončit sestavení tak, že vaše akce události ukončit s kódem než nula (0), který označuje úspěšné akce.  
  
## <a name="example-how-to-change-manifest-information-using-a-post-build-event"></a>Příklad: Jak změnit informace manifestu pomocí události po sestavení  
 Následující postup ukazuje, jak nastavit minimální verzi operačního systému v manifest aplikace pomocí příkazu .exe volat z události po sestavení (..exe soubor v adresáři projektu). Minimální verzi operačního systému je číslo jako 4.10.0.0. K tomuto účelu příkaz změní `<dependentOS>` oddíl manifestu:  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### <a name="to-create-an-exe-command-to-change-the-application-manifest"></a>Chcete-li vytvořit .exe příkaz ke změně manifestu aplikace  
  
1.  Vytvořte konzolovou aplikaci pro příkaz. Z **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **projektu**.  
  
2.  V **nový projekt** v dialogovém **jazyka Visual Basic** uzlu, vyberte **Windows** a potom **konzolové aplikace** šablony. Název projektu `ChangeOSVersionVB`.  
  
3.  V Module1.vb přidejte následující řádek na druhý `Imports` příkazy v horní části souboru:  
  
    ```  
    Imports System.Xml  
    ```  
  
4.  Přidejte následující kód v `Sub Main`:  
  
    ```  
    Sub Main()  
       Dim applicationManifestPath As String  
       applicationManifestPath = My.Application.CommandLineArgs(0)  
       Console.WriteLine("Application Manifest Path: " & applicationManifestPath.ToString)  
  
       'Get version name  
       Dim osVersion As Version  
       If My.Application.CommandLineArgs.Count >= 2 Then  
          osVersion = New Version(My.Application.CommandLineArgs(1).ToString)  
       Else  
          Throw New ArgumentException("OS Version not specified.")  
       End If  
       Console.WriteLine("Desired OS Version: " & osVersion.ToString())  
  
       Dim document As XmlDocument  
       Dim namespaceManager As XmlNamespaceManager  
       namespaceManager = New XmlNamespaceManager(New NameTable())  
       With namespaceManager  
          .AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1")  
          .AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2")  
       End With  
  
       document = New XmlDocument()  
       document.Load(applicationManifestPath)  
  
       Dim baseXPath As String  
       baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os"  
  
       'Change minimum required OS Version.  
       Dim node As XmlNode  
       node = document.SelectSingleNode(baseXPath, namespaceManager)  
       node.Attributes("majorVersion").Value = osVersion.Major.ToString()  
       node.Attributes("minorVersion").Value = osVersion.Minor.ToString()  
       node.Attributes("buildNumber").Value = osVersion.Build.ToString()  
       node.Attributes("servicePackMajor").Value = osVersion.Revision.ToString()  
  
       document.Save(applicationManifestPath)  
    End Sub  
    ```  
  
     Příkaz přijímá dva argumenty. První argument je cesta k manifestu aplikace (to znamená, složka, ve kterém procesu sestavení vytvoří manifest, obvykle Projectname.publish). Druhý argument je nová verze operačního systému.  
  
5.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
6.  Zkopírujte soubor .exe do adresáře například `C:\TEMP\ChangeOSVersionVB.exe`.  
  
 V dalším kroku vyvolání tohoto příkazu v události po sestavení, chcete-li změnit manifest aplikace.  
  
#### <a name="to-invoke-a-post-build-event-to-change-the-application-manifest"></a>K vyvolání události po sestavení změnit manifest aplikace  
  
1.  Vytvoření aplikace pro systém Windows pro projekt, který má být publikována. Z **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **projektu**.  
  
2.  V **nový projekt** v dialogovém **jazyka Visual Basic** uzlu, vyberte **Windows Classic Desktop** a potom **aplikace pro Windows Forms** Šablona. Název projektu `VBWinApp`.  
  
3.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
4.  Přejděte v Návrháři projektu **publikovat** stránky a nastavte **umístění pro publikování** k `C:\TEMP\`.  
  
5.  Publikování tohoto projektu kliknutím **publikovat**.  
  
     Soubor manifestu bude vytvořen a umístit do `C:\TEMP\VBWinApp_1_0_0_0\VBWinApp.exe.manifest`. Chcete-li zobrazit manifest, klikněte pravým tlačítkem na soubor a klikněte na **Otevřít protokolem**, pak klikněte na tlačítko **vyberte program, ze seznamu**a pak klikněte na **Poznámkový blok**.  
  
     Hledání v souboru `<osVersionInfo>` elementu. Může být například verze:  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  Přejděte v Návrháři projektu **zkompilovat** a klikněte **události sestavení** tlačítko otevřete **události sestavení** dialogové okno.  
  
7.  V **příkazový řádek události po sestavení** pole, zadejte následující příkaz:  
  
     `C:\TEMP\ChangeOSVersionVB.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     Při sestavování projektu se tento příkaz změní minimální verzi operačního systému v manifestu aplikace 5.1.2600.0.  
  
     `$(TargetPath)` Makro vyjadřuje úplnou cestu pro vytvářený spustitelný soubor. Proto bude manifest $(TargetPath) zadejte manifest aplikace vytvořený v adresáři bin. Publikování zkopíruje tento manifest umístění pro publikování, které jste nastavili dříve.  
  
8.  Projekt znovu publikujte. Přejděte na **publikovat** a klikněte na tlačítko **publikovat**.  
  
     Manifest zobrazte znovu. Zobrazit manifest, přejděte do adresáře publikovat, klikněte pravým tlačítkem na soubor a klikněte na tlačítko **Otevřít protokolem** a potom **vyberte program, ze seznamu**a potom klikněte na **Poznámkový blok**.  
  
     Verze je nyní následující:  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## <a name="see-also"></a>Viz také

[Stránka kompilovat, Návrhář projektu (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)   
[Publikovat stránku, Návrhář projektu](../ide/reference/publish-page-project-designer.md)   
[Dialogové okno Příkazový řádek události/po sestavení události před sestavením](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
[Postupy: Specifikace událostí sestavení (C#)](../ide/how-to-specify-build-events-csharp.md)