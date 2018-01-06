---
title: "Postupy: určení událostí sestavení (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-build events
- events [Visual Studio], builds
- post-build events
- build events [Visual Studio]
- builds [Visual Studio], events
ms.assetid: b4ce1ad9-5215-4b6f-b6a2-798b249aa335
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 1fcba0ef7abec3c8f5d71d34b8ff4e19e047d50b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-build-events-c"></a>Postupy: Specifikace událostí sestavení (C#)
Použití událostí sestavení Pokud chcete zadat příkazy, které před zahájením sestavení nebo po dokončení sestavení. Události sestavení jsou spuštěny pouze v případě, že sestavení úspěšně dosáhne těchto bodů v procesu sestavení.  
  
 Když na projekt je sestavena, události před sestavením jsou přidány do souboru, který je pojmenován PreBuildEvent.bat a události po sestavení jsou přidány do souboru, který je pojmenován PostBuildEvent.bat. Pokud chcete zajistit kontrolu chyb, přidejte vlastní příkazy chyb kroky sestavení.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="how-to-specify-pre-build-and-post-build-events"></a>Určení událostí před a po sestavení  
  
#### <a name="to-specify-a-build-event"></a>K určení událostí sestavení  
  
1.  V **Průzkumníku**, vyberte projekt, pro který chcete určit událost sestavení.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
3.  Vyberte **události sestavení** kartě.  
  
4.  V **příkazový řádek události před sestavením** zadejte syntaxe události sestavení.  
  
    > [!NOTE]
    >  Události před sestavením se nespustí, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
5.  V **události po sestavení příkazového řádku** zadejte syntaxe události sestavení.  
  
    > [!NOTE]
    >  Přidat `call` příkaz před příkazy všechny po sestavení, které spouštějí .bat soubory. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
6.  V **spustit události po sestavení** zadejte za jakých podmínek ke spuštění události po sestavení.  
  
    > [!NOTE]
    >  Chcete přidat zdlouhavé syntaxe, nebo vyberte některý makra ze sestavení [před sestavením událostí/po sestavení příkazového řádku dialogové okno události](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md), klikněte na tlačítko se třemi tečkami (**...** ) zobrazíte textové pole.  
  
     Syntaxe událostí sestavení může obsahovat libovolný příkaz, který je platný, na příkazovém řádku nebo v souboru bat. Název souboru batch musí předcházet `call` k zkontrolujte, zda jsou všechny následné příkazy.  
  
     **Poznámka:** Pokud události před sestavením nebo po sestavení úspěšně nedokončí, můžete ukončit sestavení tak, že vaše akce události ukončit s kódem než nula (0), který označuje úspěšné akce.  
  
## <a name="example-how-to-change-manifest-information-by-using-a-post-build-event"></a>Příklad: Jak změnit informace manifestu pomocí události po sestavení  
 Následující postup ukazuje, jak nastavit minimální verzi operačního systému v manifestu aplikace pomocí příkaz .exe, který se volá z události po sestavení (..exe soubor v adresáři projektu). Minimální verzi operačního systému je číslo jako 4.10.0.0. K tomuto účelu příkaz změní `<dependentOS>` oddíl manifestu:  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### <a name="to-create-an-exe-command-to-change-the-application-manifest"></a>Chcete-li vytvořit .exe příkaz ke změně manifestu aplikace  
  
1.  Vytvořte konzolovou aplikaci pro příkaz. Z **soubor** nabídky, přejděte na příkaz **nový**a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#**, klikněte na tlačítko **Windows**a pak klikněte na tlačítko **konzolové aplikace** šablony. Název projektu `ChangeOSVersionCS`.  
  
3.  V souboru Program.cs přidejte následující řádek na druhý `using` příkazy v horní části souboru:  
  
    ```  
    using System.Xml;  
    ```  
  
4.  V `ChangeOSVersionCS` obor názvů, nahraďte `Program` implementaci třídy následujícím kódem:  
  
    ```  
    class Program  
    {  
       /// <summary>  
       /// This function will set the minimum operating system version for a ClickOnce application.  
       /// </summary>  
       /// <param name="args">  
       /// Command Line Arguments:  
       /// 0 - Path to application manifest (.exe.manifest).  
       /// 1 - Version of OS  
       ///</param>  
       static void Main(string[] args)  
       {  
          string applicationManifestPath = args[0];  
          Console.WriteLine("Application Manifest Path: " + applicationManifestPath);  
  
          // Get version name.  
          Version osVersion = null;  
          if (args.Length >=2 ){  
             osVersion = new Version(args[1]);  
          }else{  
             throw new ArgumentException("OS Version not specified.");  
          }  
          Console.WriteLine("Desired OS Version: " + osVersion.ToString());  
  
          XmlDocument document;  
          XmlNamespaceManager namespaceManager;  
          namespaceManager = new XmlNamespaceManager(new NameTable());  
          namespaceManager.AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1");  
          namespaceManager.AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2");  
  
          document = new XmlDocument();  
          document.Load(applicationManifestPath);  
  
          string baseXPath;  
          baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os";  
  
          // Change minimum required operating system version.  
          XmlNode node;  
          node = document.SelectSingleNode(baseXPath, namespaceManager);  
          node.Attributes["majorVersion"].Value = osVersion.Major.ToString();  
          node.Attributes["minorVersion"].Value = osVersion.Minor.ToString();  
          node.Attributes["buildNumber"].Value = osVersion.Build.ToString();  
          node.Attributes["servicePackMajor"].Value = osVersion.Revision.ToString();  
  
          document.Save(applicationManifestPath);  
       }  
    }  
    ```  
  
     Příkaz přijímá dva argumenty: cesta manifest aplikace (to znamená, složka, ve kterém procesu sestavení vytvoří manifest, obvykle Projectname.publish) a nová verze operačního systému.  
  
5.  Sestavte projekt. Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
6.  Zkopírujte soubor .exe do adresáře například `C:\TEMP\ChangeOSVersionVB.exe`.  
  
 V dalším kroku vyvolejte příkaz v události po sestavení upravte manifest aplikace.  
  
#### <a name="to-invoke-a-post-build-event-to-modify-the-application-manifest"></a>K vyvolání události po sestavení upravit manifest aplikace  
  
1.  Vytvoření aplikace pro systém Windows pro projekt, který má být publikována. Z **soubor** nabídky, přejděte na příkaz **nový**a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#**, klikněte na tlačítko **Windows Classic Desktop**a potom klikněte na **aplikace pro Windows Forms** Šablona. Název projektu `CSWinApp`.  
  
3.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
4.  V Návrháři projektu, vyhledejte **publikovat** stránky a nastavte **umístění pro publikování** k `C:\TEMP\`.  
  
5.  Publikování tohoto projektu kliknutím **publikovat**.  
  
     Soubor manifestu bude vytvořen a umístit do `C:\TEMP\CSWinApp_1_0_0_0\CSWinApp.exe.manifest`. Chcete-li zobrazit manifest, klikněte pravým tlačítkem na soubor, klikněte na **Otevřít protokolem**, vyberte **vyberte program, ze seznamu**a potom klikněte na **Poznámkový blok**.  
  
     Hledání v souboru `<osVersionInfo>` elementu. Může být například verze:  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  V Návrháři projektu, klikněte **události sestavení** a klikněte **upravit po sestavení** tlačítko.  
  
7.  V **příkazový řádek události po sestavení** pole, zadejte následující příkaz:  
  
     `C:\TEMP\ChangeOSVersionCS.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     Při sestavování projektu se tento příkaz změní minimální verzi operačního systému v manifestu aplikace 5.1.2600.0.  
  
     Protože `$(TargetPath)` makro vyjadřuje úplnou cestu pro vytvářený, spustitelný soubor `$(TargetPath)`manifest specifikujete manifest aplikace vytvořený v adresáři bin. Publikování zkopíruje tento manifest umístění pro publikování, které jste nastavili dříve.  
  
8.  Projekt znovu publikujte. Přejděte na **publikovat** a klikněte na tlačítko **publikovat**.  
  
     Manifest zobrazte znovu. Zobrazit manifest, otevřete adresář publikovat, klikněte pravým tlačítkem na soubor, klikněte na **otevřete s**, vyberte **vyberte program, ze seznamu**a potom klikněte na **Poznámkový blok**.  
  
     Verze je nyní následující:  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Stránka události sestavení, Návrhář projektu (C#)](../ide/reference/build-events-page-project-designer-csharp.md)   
 [Dialogové okno Příkazový řádek události/po sestavení události před sestavením](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [Postupy: určení událostí sestavení (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md)   
 [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)